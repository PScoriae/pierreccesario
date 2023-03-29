---
title: "shuttleday.info"
draft: true
---

# About

This project, largely based on [PCPartPicker](https://pcpartpicker.com), is a rather simple webapp that lets users save and share parts lists for custom PCs.

An important thing to note about this project is that the webapp is **not** the focus of this project. Instead, I am more interested in how the DevOps Engineering and Server Adminstration side of things tie in with this webapp. DevOps aspects like CI/CD pipelines, Monitoring and Observability and general Cloud Engineering are what I'm passionate about so this webapp merely serves as a guinea pig for such DevOps processes.

With that being said, I did put in effort into creating the webapp as best I find programming in general quite gratifying. While frontend web development isn't my preference at all, it was a rather pleasant experience working with SvelteKit and was one of the primary reasons why it was chosen over other popular frameworks like React or Vue.

## Tech Stack

<table>
  <thead>
    <tr>
      <th width="500px">Infrastructure</th>
      <th width="500px">CI/CD</th>
      <th width="500px">Backend</th>
      <th width="500px">Frontend</th>
    </tr>
  </thead>
  <tbody>
    <tr width="600px">
      <td> <img src="https://img.shields.io/badge/Amazon_AWS-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white"> <img src= "https://img.shields.io/badge/Red%20Hat-EE0000?style=for-the-badge&logo=redhat&logoColor=white"> </td>
      <td> <img src="https://img.shields.io/badge/Jenkins-D24939?style=for-the-badge&logo=Jenkins&logoColor=white"> </td>
      <td> <img src="https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white"> </td>
      <td> <img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB"> </td>
    </tr>
    <tr width="600px">
      <td> <img src="https://img.shields.io/badge/Cloudflare-F38020?style=for-the-badge&logo=Cloudflare&logoColor=white"></td>
      <td> <img src="https://img.shields.io/badge/Jest-C21325?style=for-the-badge&logo=jest&logoColor=white"> </td>
      <td> <img src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white"></td>
      <td> <img src="https://img.shields.io/badge/JavaScript-323330?style=for-the-badge&logo=javascript&logoColor=F7DF1E"> </td>
    </tr>
    <tr width="600px">
      <td> <img src="https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white"> </td>
      <td> <img src="https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=white"></td>
      <td> <img src="https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white"></td>
      <td> <img src="https://img.shields.io/badge/Webpack-8DD6F9?style=for-the-badge&logo=Webpack&logoColor=white"> </td>
    </tr>
    <tr width="600px">
      <td> <img src="https://img.shields.io/badge/Terraform-7B42BC?style=for-the-badge&logo=terraform&logoColor=white "></td>
      <td>  </td>
      <td> <img src="https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white"> </td>
      <td> <img src="https://img.shields.io/badge/Material%20UI-007FFF?style=for-the-badge&logo=mui&logoColor=white""> </td>
    </tr>
    <tr width="600px">
      <td> <img src="https://img.shields.io/badge/Ansible-000000?style=for-the-badge&logo=ansible&logoColor=white "> </td>
      <td> </td>
      <td> <img src="https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=JSON%20web%20tokens&logoColor=white"> </td>
      <td> </td>
    </tr>
  </tbody>
</table>

## Source Code

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
