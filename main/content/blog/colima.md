---
title: "colima: Avoiding Docker Desktop on MacOS"
description: Because Docker Desktop is no longer free for large businesses.
summary: Because Docker Desktop is no longer free for large businesses.
date: 2024-05-12T19:13:23+08:00
cover:
  image: https://s3.ap-southeast-1.amazonaws.com/pierreccesario.com-images/blog/colima/colima-logo.webp
  alt: colima logo
tags:
  - colima
  - macos
  - howto
---

# TL;DR

```sh
brew install colima docker-cli
colima start
docker ps
```

No need to `brew install --cask docker` anymore!

# Wait, what's the problem with Docker Desktop?

A few years back, Docker Desktop for MacOS and Windows became no longer **free** for _large businesses_.
This is because of some [license changes](https://www.docker.com/blog/updating-product-subscriptions/).

Sure, for smaller businesses and personal use, you can still use it.

# Cool, I'll just use Rancher Desktop at work then.

That's a totally valid alternative.

But personally, I don't like it either.

On MacOS, if you wanted to use Docker, you had to install Docker Desktop **and** Docker CLI.
Docker Desktop handles all the nitty gritty stuff in the backend to spin up a VM for your containers, which the CLI then interacts with.
It's pretty much the same concept for Rancher.

Therein lies the problem with Rancher Desktop and Docker Desktop for me.

I really don't need another GUI to clutter my computer when all I need is a solid **CLI** tool.
I honestly can't be bothered with all the features and bloat that come with a GUI solution.

**The best solution is one where I can just use the Docker CLI just like on Linux.**

# Okay, what do you suggest then?

That's where [colima](https://github.com/abiosoft/colima) comes in.

Basically it does all that VM and container work for you, but via a CLI!

I'm not gonna pretend like I understand it all, but it uses [_containerd_](https://containerd.io) and [_lima_](https://github.com/lima-vm/lima) under the hood to allow container management, hence the name.

Plus, colima is free as in _libre_.
