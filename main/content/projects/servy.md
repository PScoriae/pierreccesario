---
title: "Servy"
description: A self-built home server/homelab for hosting personal projects and services.
summary: A self-built home server/homelab for hosting personal projects and services.
tags:
  - Linux
  - Proxmox
  - Kubernetes
  - VPN
weight: 30
---

# About

Servy is my home server that hosts all my self-hosted home services. It used to run Red Hat Enterprise Linux as its hypervisor, but now runs Proxmox VE.

Additionally, it's used as a test server for my projects before I deploy them to the cloud. For example, it also hosts a three-node Kubernetes cluster for staging any projects.

## Specifications

I needed the server to be economical as possible but with as much computing power as possible to support all the testing and sandboxing I have planned for it. I decided to go with decommissioned server parts as they offered the best performance per dollar.

| Component   | Model                      |
| ----------- | -------------------------- |
| CPU         | Intel Xeon E5 2670v2       |
| Motherboard | JGINYUE X79 LGA 2011       |
| RAM         | 32GB 1600MHz ECC DDR3      |
| HDD         | 1TB Western Digital Blue   |
| SSD         | Silicon Power P34A60 256GB |
| PSU         | Cooler Master MWE500       |

# Services

| Service            | Description                                                                                               |
| ------------------ | --------------------------------------------------------------------------------------------------------- |
| Tailscale          | VPN overlay to securely tunnel into my home network e.g. myself or an external server running Uptime Kuma |
| Adguard Home       | Internal home DNS and network-wide adblocker                                                              |
| SMB Share          | NAS for storing my files and hourly Time Machine backups                                                  |
| Kubernetes Cluster | Three-node staging environment for production projects                                                    |
| GitLab Runners     | Self-hosted runners for GitLab CI                                                                         |

For all services' live status updates, visit [status.pierreccesario.com](https://status.pierreccesario.com)

## Accomplishments

- Administration of Type 1 hypervisor (Proxmox) **(RHEL, Ubuntu, Linux Server Administration)**
- Deployed and maintained self-managed Kubernetes cluster **(Kubernetes)**
- Set up and configured internal home networking for all services **(Networking)**
- Deployed guests for remote access development **(Virtual Machines)**
