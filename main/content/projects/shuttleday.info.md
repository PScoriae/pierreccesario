---
title: "shuttleday.info"
draft: true
weight: 8
---

[aws]: https://img.shields.io/badge/Amazon_AWS-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white
[red-hat]: https://img.shields.io/badge/Red%20Hat-EE0000?style=for-the-badge&logo=redhat&logoColor=white
[terraform]: https://img.shields.io/badge/Terraform-7B42BC?style=for-the-badge&logo=terraform&logoColor=white
[ansible]: https://img.shields.io/badge/Ansible-000000?style=for-the-badge&logo=ansible&logoColor=white
[nginx]: https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white
[cloudflare]: https://img.shields.io/badge/Cloudflare-F38020?style=for-the-badge&logo=Cloudflare&logoColor=white
[jenkins]: https://img.shields.io/badge/Jenkins-D24939?style=for-the-badge&logo=Jenkins&logoColor=white
[jest]: https://img.shields.io/badge/Jest-C21325?style=for-the-badge&logo=jest&logoColor=white
[docker]: https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=white
[kubernetes]: https://img.shields.io/badge/kubernetes-326ce5.svg?&style=for-the-badge&logo=kubernetes&logoColor=white
[argocd]: https://img.shields.io/badge/Argo%20CD-1e0b3e?style=for-the-badge&logo=argo&logoColor=#d16044
[mongodb]: https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white
[nodejs]: https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white
[typescript]: https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white
[expressjs]: https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white
[jwt]: https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=JSON%20web%20tokens&logoColor=white
[react]: https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB
[javascript]: https://img.shields.io/badge/JavaScript-323330?style=for-the-badge&logo=javascript&logoColor=F7DF1E
[webpack]: https://img.shields.io/badge/Webpack-8DD6F9?style=for-the-badge&logo=Webpack&logoColor=white
[material-ui]: https://img.shields.io/badge/Material%20UI-007FFF?style=for-the-badge&logo=mui&logoColor=white

# About

I didn't really like the idea of using a WhatsApp group for organising weekly badminton sessions. Why not make a dedicated web app just for that? So, [Jonathan](https://tjonathan.com) built the frontend, and I the backend.

My friends and I now use this web app to manage every badminton session's details, its attendees and proof of payments. It makes it really easy for admins to keep track of everything all through the web app.

You might have noticed that I've deployed it onto a Kubernetes cluster and think that it's overkill. You'd be absolutely right about that. That being said, I'm genuinely interested in everything DevOps, so why not?

## Source Code

As usual, in FOSS spirit, all source code and full documentation is available on the [GitHub repo](https://github.com/shuttleday/shuttleday) should you want to host it for yourself or verify the code for security vulnerabilities.

## Tech Stack

| Infrastructure                   | CI/CD        | Container Orchestration | Backend                          | Frontend                        |
| -------------------------------- | ------------ | ----------------------- | -------------------------------- | ------------------------------- |
| ![][aws] <br> ![][red-hat]       | ![][jenkins] | ![][kubernetes]         | ![][mongodb]                     | ![][react] <br> ![][javascript] |
| ![][terraform] <br> ![][ansible] | ![][jest]    | ![][argocd]             | ![][nodejs] <br> ![][typescript] | ![][webpack]                    |
| ![][nginx]                       | ![][docker]  |                         | ![][expressjs] <br> ![][jwt]     | ![][material-ui]                |
| ![][cloudflare]                  |              |                         |                                  |                                 |

## Features

- Kubernetes HA Deployment
- Passwordless Authentication
- Badminton Session Creation and Participation
- Payment Receipt Upload and Retrieval
- Admin Tooling

## System Design and Cloud Architecture

Here's an overview of the implemented system design and hybrid cloud architecture for the project:

![cloud-architecture](https://github.com/shuttleday/shuttleday/blob/main/docs/images/systemArchitecture.webp?raw=true)

# Accomplishments

- SaaS web app that enables users to collaboratively schedule badminton sessions
- Architected multi-AWS service architecture
- Engineered multi-stage Jenkins CI/CD pipelines to automate build and deployments; ensure code quality and tests
- Configured and managed Cloudflare DNS and CDN rerouting to AWS S3 buckets complete with TLS encryption
- Integrated Google login to the onboarding flow for passwordless JWT authentication and to decrease user friction
- Ensured security of the project by with proper AWS IAM usage and securely storing hashed passwords and secrets
