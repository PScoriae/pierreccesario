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

As usual, in FOSS spirit, all source code is available on the [GitHub repo](https://github.com/shuttleday/shuttleday) should you want to host it for yourself or verify the code for security vulnerabilities.

## Tech Stack

| Infrastructure                   | CI/CD        | Container Orchestration | Backend                          | Frontend                        |
| -------------------------------- | ------------ | ----------------------- | -------------------------------- | ------------------------------- |
| ![][aws] <br> ![][red-hat]       | ![][jenkins] | ![][kubernetes]         | ![][mongodb]                     | ![][react] <br> ![][javascript] |
| ![][terraform] <br> ![][ansible] | ![][jest]    |                         | ![][nodejs] <br> ![][typescript] | ![][webpack]                    |
| ![][nginx]                       | ![][docker]  |                         | ![][expressjs] <br> ![][jwt]     | ![][material-ui]                |
| ![][cloudflare]                  |              |                         |                                  |                                 |

## Features

- Passwordless Authentication
- Badminton Session Creation and Participation
- Payment Receipt Upload and Retrieval
- Admin Tooling

## System Design and Cloud Architecture

Here's an overview of the implemented system design and cloud architecture for the project:

![cloud-architecture](https://github.com/PScoriae/PCPartsTool/blob/main/docs/cloud-arch.webp?raw=true)

# Accomplishments

- Architected and designed full stack cloud web app **(System Design/Software Architecture, AWS)**
- Leveraged IaC and CaC to programmatically set up and tear down one-click cloud infrastructure deployments with full observability and monitoring across multiple platforms **(Terraform, Ansible, Prometheus, Grafana, Docker)**
- Engineered CI/CD pipelines with GitHub Webhooks integration to automatically run Docker builds, E2E tests and deployment onto servers **(Jenkins, Ansible, Playwright, Docker Compose, AWS EC2, RHEL)**
- Designed and implemented a SvelteKit MongoDB CRUD WebApp with Tailwind CSS **(SvelteKit, MongoDB, TailwindCSS)**
- Composed and formatted precise and informative documentation to aid understanding and deployment process of the project, providing explanations of our DevOps practices **(Documentation, Markdown)**

Read the official full-fat documentation in the [GitHub repository](https://github.com/PScoriae/PCPartsTool).
