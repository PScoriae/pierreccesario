---
title: "PCPartsTool"
description: A SvelteKit Webapp that lets users save and share parts lists for custom PCs | Deployed on AWS with CI/CD
summary: A SvelteKit Webapp that lets users save and share parts lists for custom PCs | Deployed on AWS with CI/CD
tags:
  - SvelteKit
  - TypeScript
  - MongoDB
  - AWS
  - AWS EC2
  - Nginx
  - Jenkins CI/CD
  - Docker
  - Cloudflare
  - Terraform
  - Ansible
  - Website Hosting and Deployment
  - Documentation
  - GitHub
weight: 5
---

## About

This project, largely based on [PCPartPicker](https://pcpartpicker.com), is a rather simple webapp that lets users save and share parts lists for custom PCs.

An important thing to note about this project is that the webapp is **not** the focus of this project. Instead, I am more interested in how the DevOps Engineering and Server Adminstration side of things tie in with this webapp. DevOps aspects like CI/CD pipelines, Monitoring and Observability and general Cloud Engineering are what I'm passionate about so this webapp merely serves as a guinea pig for such DevOps processes.

With that being said, I did put in effort into creating the webapp as best I find programming in general quite gratifying. While frontend web development isn't my preference at all, it was a rather pleasant experience working with SvelteKit and was one of the primary reasons why it was chosen over other popular frameworks like React or Vue. If you'd like to see what you can do with the site, you can go ahead and check it out at [pcpartstool.pierreccesario.com](https:/pcpartstool.pierreccesario.com)

## Accomplishments

- Leveraged Terraform, Ansible, Prometheus and Grafana to programmatically set up and tear down one-click cloud infrastructure deployments with full observability and monitoring **(Terraform, Ansible, Prometheus, Grafana, Docker)**
- Engineered Jenkins pipeline with GitHub Webhooks integration to automatically run SonarQube quality gates, Playwright E2E testing, Docker builds and deployment onto servers **(Jenkins, SonarQube, Playwright, Docker Compose, AWS EC2)**
- Designed and implemented a SvelteKit MongoDB CRUD WebApp with Tailwind CSS **(SvelteKit, MongoDB, TailwindCSS)**
- Composed and formatted precise and informative documentation to aid understanding and deployment process of the project **(Documentation, Markdown)**