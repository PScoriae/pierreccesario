---
title: "shuttleday.info"
description: The self-hosted Badminton session scheduling web app.
summary: The self-hosted Badminton session scheduling web app.
cover:
  image: https://s3.ap-southeast-1.amazonaws.com/pierreccesario.com-images/projects/shuttleday.info/banner.webp
  alt: shuttleday cover
tags:
  - Kubernetes
  - Kustomize
  - ArgoCD
  - JWT
  - Express
  - TypeScript
  - Node.js
  - Terraform
  - Ansible
  - Docker
  - GitHub Actions
  - AWS
  - Cloudflare
  - GitHub
  - DevOps
  - GitOps
  - Multi-cloud
weight: 8
---

[aws]: https://img.shields.io/badge/AWS-FF9900?style=for-the-badge&logo=amazonwebservices&logoColor=white
[digitalocean]: https://img.shields.io/badge/Digital_Ocean-0080FF?style=for-the-badge&logo=DigitalOcean&logoColor=white
[red-hat]: https://img.shields.io/badge/Red%20Hat-EE0000?style=for-the-badge&logo=redhat&logoColor=white
[terraform]: https://img.shields.io/badge/Terraform-7B42BC?style=for-the-badge&logo=terraform&logoColor=white
[ansible]: https://img.shields.io/badge/Ansible-000000?style=for-the-badge&logo=ansible&logoColor=white
[nginx]: https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white
[cloudflare]: https://img.shields.io/badge/Cloudflare-F38020?style=for-the-badge&logo=Cloudflare&logoColor=white
[github-actions]: https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white
[jest]: https://img.shields.io/badge/Jest-C21325?style=for-the-badge&logo=jest&logoColor=white
[kubernetes]: https://img.shields.io/badge/kubernetes-326ce5.svg?&style=for-the-badge&logo=kubernetes&logoColor=white
[argocd]: https://img.shields.io/badge/Argo%20CD-1e0b3e?style=for-the-badge&logo=argo&logoColor=#d16044
[mongodb]: https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white
[nodejs]: https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white
[typescript]: https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white
[expressjs]: https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white
[jwt]: https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=JSON%20web%20tokens&logoColor=white
[react]: https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB
[javascript]: https://img.shields.io/badge/JavaScript-323330?style=for-the-badge&logo=javascript&logoColor=F7DF1E
[vite]: https://img.shields.io/badge/Vite-B73BFE?style=for-the-badge&logo=vite&logoColor=FFD62E
[material-ui]: https://img.shields.io/badge/Material%20UI-007FFF?style=for-the-badge&logo=mui&logoColor=white
[tailwind]: https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white

## About

I didn't really like the idea of using a WhatsApp group for organising weekly badminton sessions.
Why not make a dedicated web app just for that?
So, [Jonathan](https://tjonathan.com) built the frontend, and I the backend.

My friends and I now use this web app to manage every badminton session's details, its attendees and proof of payments.
It makes it really easy for admins to keep track of everything all through the web app.

You might have noticed that I've deployed it onto a Kubernetes cluster and think that it's overkill.
You'd be absolutely right about that.
That being said, I genuinely like Kubernetes, so why not?

### DeepWiki Documentation

If you'd like to dive into technical details, feel free to visit the DeepWiki documentation [here.](https://deepwiki.com/shuttleday/shuttleday)

It's not 100% accurate, but it did a pretty damn good job!

### Source Code

As usual, in FOSS spirit, all source code and full documentation is available on the [GitHub repo](https://github.com/shuttleday/shuttleday) should you want to host it for yourself or verify the code for security vulnerabilities.

### Developer Highlights

- GitOps Workflow
- Kubernetes HA Deployment
- Automated staging and production Deployments
- Bastion-host restricted staging environment
- Automated setup and configuration with Terraform and Ansible code
- Hybrid Cloud architecture

### User Features

- Passwordless authentication
- Badminton session creation and participation
- Custom groups (rooms)
- Payment receipt upload and retrieval
- Admin tooling

### Tech Stack

| Infrastructure                               | CI/CD                             | Backend                             | Frontend                      |
| -------------------------------------------- | --------------------------------- | ----------------------------------- | ----------------------------- |
| ![aws][aws] ![digitalocean][digitalocean]    | ![github-actions][github-actions] | ![mongodb][mongodb]                 | ![react][react] ![vite][vite] |
| ![redhat][red-hat] ![kubernetes][kubernetes] | ![argocd][argocd]                 | ![typescript][typescript]           | ![javascript][javascript]     |
| ![terraform][terraform] ![ansible][ansible]  | ![jest][jest]                     | ![nodejs][nodejs]                   | ![tailwind][tailwind]         |
| ![nginx][nginx] ![cloudflare][cloudflare]    |                                   | ![expressjs][expressjs] ![jwt][jwt] | ![material-ui][material-ui]   |

### System Design and Cloud Architecture

Here's an overview of the implemented system design and hybrid cloud architecture for the project:

![cloud-architecture](https://s3.ap-southeast-1.amazonaws.com/pierreccesario.com-images/projects/shuttleday.info/cloud-arch.webp)

## Achievements

- Architected GitOps hybrid-cloud deployments; automated staging and prod environments; system health notifiers
- Engineered secure GitHub Actions CI + GitOps ArgoCD pipelines; code quality, tests and automated deployments
- Developed robust Kubernetes manifests for containerised deployments
- Configured automated Cloudflare DNS records to cloud resources with Terraform and Ansible
- Integrated Google login to the onboarding flow for passwordless JWT authentication and to decrease user friction
- Ensured security of cloud resources; proper AWS IAM usage, hashed secrets, principle of least privilege
- Liaised with stakeholders to implement feature requests
