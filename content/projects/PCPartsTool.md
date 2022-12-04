---
title: "PCPartsTool"
description: A SvelteKit Web app | Deployed on AWS, Cloudflare with Jenkins, Terraform and Ansible
summary: A SvelteKit Web app | Deployed on AWS, Cloudflare with Jenkins, Terraform and Ansible
cover:
  image: img/pcpartstool-cover.webp
  alt: PCPartsTool Logo
tags:
  - SvelteKit
  - TypeScript
  - JavaScript
  - Tailwind CSS
  - MongoDB
  - Playwright
  - AWS
  - AWS EC2
  - AWS S3
  - Nginx
  - Jenkins CI/CD
  - Docker
  - Cloudflare
  - Terraform
  - Ansible
  - Prometheus
  - Grafana
  - Red Hat Enterprise Linux
  - Website Hosting and Deployment
  - System Design
  - Software Architecture
  - Documentation
  - GitHub
  - DevOps
weight: 5
---

# About

This project, largely based on [PCPartPicker](https://pcpartpicker.com), is a rather simple webapp that lets users save and share parts lists for custom PCs.

An important thing to note about this project is that the webapp is **not** the focus of this project. Instead, I am more interested in how the DevOps Engineering and Server Adminstration side of things tie in with this webapp. DevOps aspects like CI/CD pipelines, Monitoring and Observability and general Cloud Engineering are what I'm passionate about so this webapp merely serves as a guinea pig for such DevOps processes.

With that being said, I did put in effort into creating the webapp as best I find programming in general quite gratifying. While frontend web development isn't my preference at all, it was a rather pleasant experience working with SvelteKit and was one of the primary reasons why it was chosen over other popular frameworks like React or Vue. If you'd like to see what you can do with the site, you can go ahead and check it out at [pcpartstool.pierreccesario.com](https://pcpartstool.pierreccesario.com)

## Source Code

**Note:** The PCPartsTool project consists of multiple repositories. Here are all the related repositories:

| Repository                                                             | Built With                                                                                                                                                                                                                                                               | Description                                                         |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------- |
| [PCPartsTool](https://github.com/PScoriae/PCPartsTool)                 | [SvelteKit](https://kit.svelte.com), [TypeScript](https://www.typescriptlang.org/), [Tailwind CSS](https://tailwindcss.com), [MongoDB](https://mongodb.com), [Jenkins](https://www.jenkins.io/), [Docker](https://www.docker.com/), [Playwright](https://playwright.dev) | The SvelteKit MongoDB WebApp                                        |
| [PCPartsTool-Scraper](https://github.com/PScoriae/PCPartsTool-Scraper) | [JavaScript](https://www.javascript.com/), [Jenkins](https://www.jenkins.io/), [Docker](https://www.docker.com/)                                                                                                                                                         | Scraping Script to Gather E-commerce Item Data                      |
| [terraform-infra](https://github.com/PScoriae/terraform-infra)         | [Terraform](https://terraform.com), [Cloudflare](https://cloudflare.com), [AWS](https://aws.amazon.com)                                                                                                                                                                  | Terraform IaC for PCPartsTool Cloud Infrastructure                  |
| [ansible-ec2](https://github.com/PScoriae/ansible-ec2)                 | [Ansible](https://ansible.com), [Prometheus](https://prometheus.io), [Grafana](https://grafana.com), [Nginx](https://nginx.com), [AWS](https://aws.amazon.com)                                                                                                           | Ansible CaC for AWS EC2 Bootstraping, Observability and Maintenance |

## Cloud Architecture

![cloud-architecture](https://github.com/PScoriae/PCPartsTool/blob/main/docs/cloud-arch.webp?raw=true)

# Accomplishments

- Architected and designed full stack cloud web app **(System Design/Software Architecture, AWS)**
- Leveraged IaC and CaC to programmatically set up and tear down one-click cloud infrastructure deployments with full observability and monitoring across multiple platforms **(Terraform, Ansible, Prometheus, Grafana, Docker)**
- Engineered CI/CD pipelines with GitHub Webhooks integration to automatically run Docker builds, E2E tests and deployment onto servers **(Jenkins, Ansible, Playwright, Docker Compose, AWS EC2, RHEL)**
- Designed and implemented a SvelteKit MongoDB CRUD WebApp with Tailwind CSS **(SvelteKit, MongoDB, TailwindCSS)**
- Composed and formatted precise and informative documentation to aid understanding and deployment process of the project, providing explanations of our DevOps practices **(Documentation, Markdown)**

Read the official full-fat documentation in the [GitHub repository](https://github.com/PScoriae/PCPartsTool).
