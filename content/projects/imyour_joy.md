---
title: "imyour_joy"
description: An open source self-deployable Dockerized Discord.js bot complete with CI/CD written in TypeScript (previously Python).
summary: An open source self-deployable Dockerized Discord.js bot complete with CI/CD written in TypeScript (previously Python).
tags:
- TypeScript
- Discord.js
- Docker
- Jenkins CI/CD
- AWS EC2
- DevOps
- Documentation
- kpop
weight: 10
---

## About
In its current state, this is a Kpop themed Discord bot that with features that appeal to Kpop fans.

Complying with Discord's announcement regarding _[Message Content Access Deprecation for Verified Bots](https://support-dev.discord.com/hc/en-us/articles/4404772028055-Message-Content-Access-Deprecation-for-Verified-Bots)_, this bot only uses Slash Commands. Though this change only applies to Verified Bots, I still want to use Slash Commands so that I hopefully don't encounter any headaches in the future.

### Accomplishments
- Developed a customised Jenkins CI/CD Pipeline that integrates with GitHub Webhooks to automatically run Docker builds and deployment onto servers **(Jenkins, Docker)**
- Engineered and implemented YouTube and Spotify Web API integrations to periodically send relevant YouTube links from a randomised list of songs in a Spotify playlist **(TypeScript, Python, Cron Job)**
- Developed a pipeline for automated image web scraping and integration with Discord servers **(Cheerio, BeautifulSoup4)**
- Composed and formatted precise and informative documentation to aid understanding and deployment process of the project **(Documentation, Markdown)**

Read the official full-fat documentation in the official [GitHub repository](https://github.com/PScoriae/imyour_joy).

### Built With

- [TypeScript](https://www.typescriptlang.org/)
- [Discord.js](https://discord.js.org/#/)
- [Docker](https://www.docker.com/)
- [Jenkins](https://www.jenkins.io/)