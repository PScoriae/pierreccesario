<div align='center'>

[![pierreccesario.com CI](https://github.com/PScoriae/pierreccesario/actions/workflows/main.yml/badge.svg)](https://github.com/PScoriae/pierreccesario/actions/workflows/main.yml)

[![music.pierreccesario.com CI](https://github.com/PScoriae/pierreccesario/actions/workflows/music.yml/badge.svg)](https://github.com/PScoriae/pierreccesario/actions/workflows/music.yml)

<p>
  <a href="https://github.com/PScoriae/pierreccesario/blob/main/LICENSE">
    <img src="https://img.shields.io/badge/license-WTFPL-brightgreen?style=for-the-badge">
  </a>
</p>
<p>
  <img src="main/static/android-chrome-512x512.png" width=300>
</p>

## pierreccesario.com

</div>

<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about">About</a>
    </li>
    <li><a href="#initial-setup">Initial Setup</a></li>
    <li>
      <a href="#deployment-configuration">Deployment Configuration</a>
      <ul>
        <li><a href="#ec2-configuration">EC2 Configuration</a></li>
        <li><a href="#jenkins-configuration">Jenkins Configuration</a></li>
        <li><a href="#github-webhook">GitHub Webhook</a></li>
      </ul>
    </li>
    <li><a href="#acknowledgements">Acknowledgements</a></li>
  </ol>
</details>
<hr/>

## About

Essentially, this site is my .com, so it'll have everything that pertains to me and my career that I think you'll find important or fascinating whether you're a recruiter or someone getting to know me better.
Since this website can also act as a platform for me to express my opinions about things, I may also post some reviews or opinion articles here too.

To get into the technical aspect of this website, it leverages the power of [Hugo](https://gohugo.io/) to generate a static website and its HTML pages from source markdown files.
All of this is automatically built with a custom GitHub Actions Workflow and is deployed onto [S3.](https://aws.amazon.com/s3/)
The site then sits behind [Cloudflare's](https://www.cloudflare.com/) robust CDN and DNS.

### Built With

- [Hugo](https://gohugo.io/)
- [GitHub Actions](https://github.com/features/actions)
- [AWS S3](https://aws.amazon.com/s3/)
- [Cloudflare](https://www.cloudflare.com/)

## Initial Setup

You'll need a few things in the cloud set up:

1. AWS S3

2. Cloudflare

Refer to the included links in the [Acknowledgements](#acknowledgements) section to set them up correctly with the correct Security Control Groups and settings.

## Deployment Configuration

With the infrastructure set up, a **manual** deployment looks a little something like this:

1. First, `cd` into the directory for the site you wish to build e.g. `music`.

2. Run the `hugo` command on your development machine to create the website files in the `public/` folder.

3. Use the AWS S3 web console to upload all files in the `public/` folder to the root domain S3 bucket.

For me, this becomes a rather tedious and repetitive process, especially when you want to make multiple successive changes quite frequently.
Unsurprisingly, it also becomes the perfect task for automation purposes.

This section will detail how to set up the Jenkins CI/CD pipeline using the aforementioned services.

### Hugo `config.yaml`

All you need to do here is update `deployment.target.URL` in the `config.yaml` file for your site with the correct S3 bucket URL.

### GitHub Actions Workflow

The naive method to upload files to S3 using a CI tool is to use the `aws s3 cp` command.
The issue with this is that it copies the entire `/public` folder into S3, even if the files did not change - the upload isn't incremental.
This becomes a cost issue since [S3 charges based on the number of PUT calls you make](https://aws.amazon.com/s3/pricing/).
Ergo, your cost goes up proportionally with how many times you deploy how big your project is; this is clearly an antipattern for DevOps!

The clear and easy solution is to use the built in [`hugo deploy`](https://gohugo.io/hosting-and-deployment/hugo-deploy/) command.
Under the hood, it uses the author's own [`s3deploy`](https://github.com/bep/s3deploy) project, which "uses ETag hashes to check if a file has changed, which makes it optimal in combination with static site generators like Hugo".

Essentially, all you need to do is configure the `aws-actions/configure-aws-credentials@v2` plugin with the IAM role that has access to your S3 bucket.

## Acknowledgements

| Source                                                                                                                                                      | Description                                                                                |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| [Official AWS Guide to hosting a static website with S3](https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteHosting.html)                         | Walks you through everything you need to know to setup AWS S3 buckets to host your website |
| [Hosting a static website: Amazon S3 + Cloudflare](https://medium.com/@hranicka/hosting-a-static-website-amazon-s3-cloudflare-127b57a13461)                 | Great guide to get you up and running                                                      |
| [Official Cloudflare Guide](https://support.cloudflare.com/hc/en-us/articles/360037983412-Configuring-an-Amazon-Web-Services-static-site-to-use-Cloudflare) | Detailed Cloudflare guide for Cloudflare and AWS hosting                                   |
| [jeff-h's StackOverflow answer](https://stackoverflow.com/a/70872265)                                                                                       | Explains Cloudflare Auto-minify setting to prevent broken CSS                              |
