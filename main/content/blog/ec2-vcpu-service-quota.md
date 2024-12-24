---
title: "EC2 vCPU Quotas: Unlock Hidden Cost Savings and Scalability"
description: There are quotas for EC2 spot and on-demand instances?
summary: There are quotas for EC2 spot and on-demand instances?
date: 2024-12-25T01:30:00+08:00
cover:
  image: https://s3.ap-southeast-1.amazonaws.com/pierreccesario.com-images/blog/ec2-vcpu-service-quota/banner.webp
  alt: article image
tags:
  - AWS
  - cost
  - MoneyLion
---

[screenshot]: https://s3.ap-southeast-1.amazonaws.com/pierreccesario.com-images/blog/ec2-vcpu-service-quota/screenshot.webp

# TL;DR

Check your Spot vCPU and On-demand vCPU quotas ASAP.

You could be artifically limiting how many Spot instances you're spinning up, thereby paying more for On-demand instances instead of provisioning Spot.

Or, it could be how many On-demand instances you can spin up, which limits the scalablility of your platform.

# Background

I was investigating the root cause for a ticket and I decided to venture into the Service Quota page of AWS thinking I may find some clues in there.
I spotted the EC2 Service Quota page and it piqued my curiosity — what kind of quotas do they have for it?
I chanced upon two rather critical quotas: Spot vCPU and On-demand vCPU instance requests.

I never knew there were quotas for these!

![][screenshot]

# Unlock Free Savings

For our staging EKS clusters, we prioritise spot instances since we don't mind the interruptions for added savings.
Whenever we inspect the kinds of nodes Karpenter provisions, we would see a sparse distribution of spot instances among the on-demand instances.
"Probably because there's no spot capacity available.", or so we thought.

When I stumbled across the quota, the CloudWatch metrics showed we were **always** maxed out. **Always**.

After bumping it up, it began to rapidly max out.
I requested another bump and it hit the cap again, which means Karpenter **had** to spin up on-demand instances instead.
Eventually, it began to stabilise after increasing it enough.

We primarily use on-demand instances

Holy shit. We've been missing out on all these savings for so long. Holy shit.

# Scale Without Limits

As part of our MrBeast campaign, we needed to prescale our EKS cluster to handle the increased load.

Had we not increased our on-demand quota, we would've hit a roadblock — an artificial roadblock that limits our cluster's scalability.

That's absolutely **detrimental** to the business and you never want to be in a situation like that. It could be costly if not addressed promptly.

# "Wait, I've never had to increase this before."

Yep.
When I saw our initial quotas, they were at some weird arbitrary integer like 1838.

I would imagine AWS uses an algorithm which tracks your usage patterns to preemptively and silently increase your quota.

However, if you're in a situation like us where we need to prescale our infrasturcture in anticipation of a traffic spike, you'll definitely want to make a request beforehand.
If not, at least for the savings from spot!

# Monitoring and Alerting EC2 vCPU Quotas

Lucky for you and I, we can easily set up monitoring and alerting for these quotas' usage.
So, I created a simple Terraform module to help us increase the quota and manage the CloudWatch alarms for us.

Basically, you pass in the quota value you desire for the service quota code you want and it will increase along with the CloudWatch alarm thresholds.

The underlying [aws_servicequotas_service_quota](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/servicequotas_service_quota) resource sends a request increase, just like how you would do it through the console.
This means the quota isn't increased immediately, but I believe it's better to update the CloudWatch alarms based on the quota value input instead of the current value of the quota.
In our experience, the requests are always approved anyway, so it's fine to increase the alarm thresholds preemptively.
Making the CloudWatch alarms use the current value means you will have to `terraform apply` the state again after the quota has been approved.
Terrible DX.
