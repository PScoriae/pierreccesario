---
title: "pierreccesario.com"
description: The very portfolio website that you're currently on!
summary: The very portfolio website that you're currently on!
cover:
  image: img/banner_pierreccesariocom.webp
  alt: pierreccesario cover
tags:
  - Hugo
  - GitHub Actions
  - AWS
  - Cloudflare
  - Markdown
  - GitHub
  - Terraform
  - Ansible
  - DevOps
  - GitOps
weight: 10
---

[aws]: https://img.shields.io/badge/Amazon_AWS-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white
[redhat]: https://img.shields.io/badge/Red%20Hat-EE0000?style=for-the-badge&logo=redhat&logoColor=white
[terraform]: https://img.shields.io/badge/Terraform-7B42BC?style=for-the-badge&logo=terraform&logoColor=white
[ansible]: https://img.shields.io/badge/Ansible-000000?style=for-the-badge&logo=ansible&logoColor=white
[cloudflare]: https://img.shields.io/badge/Cloudflare-F38020?style=for-the-badge&logo=Cloudflare&logoColor=white
[github-actions]: https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white
[uptime-kuma]: https://img.shields.io/badge/Uptime_Kuma-84df99?style=for-the-badge&logo=uptime-kuma&logoColor=white
[github]: https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white
[hugo]: https://img.shields.io/badge/Hugo-FF4088?style=for-the-badge&logo=hugo&logoColor=white
[markdown]: https://img.shields.io/badge/Markdown-000000?style=for-the-badge&logo=markdown&logoColor=white

# About

Essentially, this site is my .com, so it'll have everything that pertains to me and my career that I think you'll find important or interesting whether you're a recruiter or someone getting to know me better. Since this website can also act as a platform for me to express my opinions about things, I may also post some reviews or opinion articles here too.

To get into the technical aspect of this website, it leverages the power of [Hugo](https://gohugo.io/) to generate a static website and its HTML pages from source markdown files. All of this is automatically deployed with [Jenkins](https://www.jenkins.io/) from the GitHub repository using AWS services like [EC2](https://aws.amazon.com/ec2/) and [S3](https://aws.amazon.com/s3/) along with [Cloudflare's](https://www.cloudflare.com/) robust CDN and DNS.

Read the official full-fat how-to and documentation in the [GitHub repository](https://github.com/PScoriae/pierreccesario).

## Tech Stack

| Infrastructure                   | Monitoring       | CI/CD               | Frontend      |
| -------------------------------- | ---------------- | ------------------- | ------------- |
| ![][aws] <br> ![][redhat]        | ![][uptime-kuma] | ![][github-actions] | ![][hugo]     |
| ![][terraform] <br> ![][ansible] |                  |                     | ![][markdown] |
| ![][cloudflare]                  |                  |                     |               |

# Accomplishments

- Developed a customised Jenkins CI/CD Pipeline that integrates with GitHub Webhooks to automatically run Hugo builds on AWS EC2 and deployments to AWS S3 buckets **(Hugo, Jenkins, AWS S3, AWS EC2)**
- Set up and configure Cloudflare DNS and CDN rerouting to AWS S3 buckets complete with TLS/SSL encryption for secure connections **(Cloudflare, AWS S3, Web Hosting)**
- Composed and formatted precise and informative documentation to aid understanding and deployment process of the project **(Documentation, Markdown)**
