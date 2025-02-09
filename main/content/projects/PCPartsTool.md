---
title: "PCPartsTool"
description: A SvelteKit Web app | Deployed on AWS, Cloudflare with Jenkins, Terraform and Ansible
summary: A SvelteKit Web app | Deployed on AWS, Cloudflare with Jenkins, Terraform and Ansible
cover:
  image: https://s3.ap-southeast-1.amazonaws.com/pierreccesario.com-images/projects/pcpartstool/banner.webp
  alt: PCPartsTool Logo
tags:
  - SvelteKit
  - TypeScript
  - Tailwind CSS
  - MongoDB
  - Playwright
  - Nginx
  - Jenkins
  - Docker
  - Cloudflare
  - Terraform
  - Ansible
  - Prometheus
  - Grafana
  - GitHub
  - DevOps
  - AWS
weight: 9
---

[aws]: https://img.shields.io/badge/AWS-FF9900?style=for-the-badge&logo=amazonwebservices&logoColor=white
[red-hat]: https://img.shields.io/badge/Red%20Hat-EE0000?style=for-the-badge&logo=redhat&logoColor=white
[terraform]: https://img.shields.io/badge/Terraform-7B42BC?style=for-the-badge&logo=terraform&logoColor=white
[ansible]: https://img.shields.io/badge/Ansible-000000?style=for-the-badge&logo=ansible&logoColor=white
[nginx]: https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white
[cloudflare]: https://img.shields.io/badge/Cloudflare-F38020?style=for-the-badge&logo=Cloudflare&logoColor=white
[jenkins]: https://img.shields.io/badge/Jenkins-D24939?style=for-the-badge&logo=Jenkins&logoColor=white
[playwright]: https://img.shields.io/badge/Playwright-45ba4b?style=for-the-badge&logo=Playwright&logoColor=white
[docker]: https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=white
[prometheus]: https://img.shields.io/badge/Prometheus-000000?style=for-the-badge&logo=prometheus&labelColor=000000
[grafana]: https://img.shields.io/badge/Grafana-F2F4F9?style=for-the-badge&logo=grafana&logoColor=orange&labelColor=F2F4F9
[mongodb]: https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white
[svelte]: https://img.shields.io/badge/Svelte-4A4A55?style=for-the-badge&logo=svelte&logoColor=FF3E00
[sveltekit]: https://img.shields.io/badge/SvelteKit-FF3E00?style=for-the-badge&logo=Svelte&logoColor=white
[typescript]: https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white
[tailwind]: https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white
[daisy-ui]: https://img.shields.io/badge/Daisy%20UI-522bbe?style=for-the-badge&logo=daisyui&logoColor=white

## About

This project, largely based on [PCPartPicker](https://pcpartpicker.com), is a rather simple webapp that lets users save and share parts lists for custom PCs.

An important thing to note about this project is that the webapp is **not** the focus of this project. Instead, I am more interested in how the DevOps Engineering and Server Adminstration side of things tie in with this webapp. DevOps aspects like CI/CD pipelines, Monitoring and Observability and general Cloud Engineering are what I'm passionate about so this webapp merely serves as a guinea pig for such DevOps processes.

With that being said, I did put in effort into creating the webapp as best I find programming in general quite gratifying. While frontend web development isn't my preference at all, it was a rather pleasant experience working with SvelteKit and was one of the primary reasons why it was chosen over other popular frameworks like React or Vue.

### Source Code

Read the official full-fat documentation in the [GitHub repository](https://github.com/PScoriae/PCPartsTool).

### Tech Stack

| Infrastructure                              | DevOps                                        | Backend                   | Frontend              |
| ------------------------------------------- | --------------------------------------------- | ------------------------- | --------------------- |
| ![aws][aws] ![red-hat][red-hat]             | ![jenkins][jenkins]                           | ![mongodb][mongodb]       | ![svelte][svelte]     |
| ![terraform][terraform] ![ansible][ansible] | ![playwright][playwright]                     | ![sveltekit][sveltekit]   | ![tailwind][tailwind] |
| ![nginx][nginx]                             | ![docker][docker]                             | ![typescript][typescript] | ![daisy-ui][daisy-ui] |
| ![cloudflare][cloudflare]                   | ![prometheus][prometheus] ![grafana][grafana] |                           |                       |

**Note:** The PCPartsTool project consists of multiple repositories. Here are all the related repositories:

| Repository                                                             | Description                                                         |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------- |
| [PCPartsTool](https://github.com/PScoriae/PCPartsTool)                 | The SvelteKit MongoDB WebApp                                        |
| [PCPartsTool-Scraper](https://github.com/PScoriae/PCPartsTool-Scraper) | Scraping Script to Gather E-commerce Item Data                      |
| [terraform-infra](https://github.com/PScoriae/terraform-infra)         | Terraform IaC for PCPartsTool Cloud Infrastructure                  |
| [ansible-ec2](https://github.com/PScoriae/ansible-ec2)                 | Ansible CaC for AWS EC2 Bootstraping, Observability and Maintenance |

### System Design and Cloud Architecture

Here's an overview of the implemented system design and cloud architecture for the project:

![cloud-architecture](https://s3.ap-southeast-1.amazonaws.com/pierreccesario.com-images/projects/pcpartstool/cloud-arch.webp)

## Findings

Seeing as this project also served as my degree's final year project, I had to make an accompanying report for my findings. I do not plan to publish said report, but in case you are someone who has seen my resume, you might be wondering how I got the claimed numbers for the reduced deployment times due to the use of Ansible, Terraform or Jenkins. Hence, here's the data for that:

![terraform](https://s3.ap-southeast-1.amazonaws.com/pierreccesario.com-images/projects/pcpartstool/terraform.webp)
![ansible](https://s3.ap-southeast-1.amazonaws.com/pierreccesario.com-images/projects/pcpartstool/ansible.webp)
![jenkins](https://s3.ap-southeast-1.amazonaws.com/pierreccesario.com-images/projects/pcpartstool/jenkins.webp)
![playwright](https://s3.ap-southeast-1.amazonaws.com/pierreccesario.com-images/projects/pcpartstool/playwright.webp)

## Achievements

- Architected and designed full stack cloud web app
- Leveraged IaC and CaC to programmatically set up and tear down one-click cloud infrastructure deployments with full observability and monitoring across multiple platforms
- Engineered CI/CD pipelines with GitHub Webhooks integration to automatically run Docker builds, E2E tests and deployment onto servers
- Designed and implemented a SvelteKit MongoDB CRUD WebApp with Tailwind CSS
- Composed and formatted precise and informative documentation to aid understanding and deployment process of the project, providing explanations of our DevOps practices
