<div align='center'>
<p>
  <a href="https://linkedin.com/in/pierreccesario">
    <img src="https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555">
  </a>
</p>
<p>
  <a href="https://github.com/PScoriae/pierreccesario/blob/main/LICENSE">
    <img src="https://img.shields.io/github/license/othneildrew/Best-README-Template.svg?style=for-the-badge">
  </a>
</p>
<p>
  <img src="./static/android-chrome-512x512.png" width=300>
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

Essentially, this site is my .com, so it'll have everything that pertains to me and my career that I think you'll find important or fascinating whether you're a recruiter or someone getting to know me better. Since this website can also act as a platform for me to express my opinions about things, I may also post some reviews or opinion articles here too.

To get into the technical aspect of this website, it leverages the power of [Hugo](https://gohugo.io/) to generate a static website and its HTML pages from source markdown files. All of this is automatically deployed with [Jenkins](https://www.jenkins.io/) from the GitHub repository using AWS services like [EC2](https://aws.amazon.com/ec2/) and [S3](https://aws.amazon.com/s3/) along with [Cloudflare's](https://www.cloudflare.com/) robust CDN and DNS.

### Built With

- [Hugo](https://gohugo.io/)
- [Jenkins](https://www.jenkins.io/)
- [AWS EC2](https://aws.amazon.com/ec2/)
- [AWS S3](https://aws.amazon.com/s3/)
- [Cloudflare](https://www.cloudflare.com/)

## Initial Setup

You'll need a few things set up, mainly for web hosting and the Jenkins CI/CD pipeline:

1. Your Hugo Website

2. AWS S3

3. AWS EC2

4. Cloudflare

Refer to the included links in the [Acknowledgements](#acknowledgements) section to set them up correctly with the correct Security Control Groups and settings.

## Deployment Configuration

With the infrastructure set up, a **manual** deployment looks a little something like this:

1. Run the `hugo` command on your development machine to create the website files in the `public/` folder.

2. Use the AWS S3 web console to upload all files in the `public/` folder to the root domain S3 bucket.

For me, this becomes a rather tedious and repetitive process, especially when you want to make multiple successive changes quite frequently.
Unsurprisingly, it also becomes the perfect task for automation purposes.

This section will detail how to set up the Jenkins CI/CD pipeline using the aforementioned services.

### EC2 Configuration

For this project, since the static site is being hosted on the S3 bucket and no active server-side rendering is used, an AWS EC2 instance will be used to host the Jenkins CI/CD server.

As such, you'll need the following packages on your EC2 instance to be installed:

1. Jenkins

2. Hugo

3. AWS CLI

Since the S3 bucket will have to communciate with Cloudflare and EC2, the appropriate Security Groups will have to be configured.

### Jenkins Configuration

Essentially, you'll need to create a new Pipeline that points to the Jenkinsfile in the repository.

Then, the following settings should be configured accordingly:

- Discard old builds

- GitHub hook trigger for GITScm polling

- Excluded regions

### GitHub Webhook

The endpoint that the webhook will have to push a POST request to will be based on your EC2 server's Public IPv4 DNS address. Then, you'll need to append the port of the Jenkins instance (8080 by default) as well as the endpoint that Jenkins is expecting.

So, the endpoint in the GitHub Webhooks section of your repository should look a little something like this:

`ec2-12-34-56-789.ap-southeast-1.compute.amazonaws.com:8080/github-webhook/`

Be sure to append the trailing slash at the end or it won't work.

## Acknowledgements

| Source                                                                                                                                                      | Description                                                                                |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| [Official AWS Guide to hosting a static website with S3](https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteHosting.html)                         | Walks you through everything you need to know to setup AWS S3 buckets to host your website |
| [Hosting a static website: Amazon S3 + Cloudflare](https://medium.com/@hranicka/hosting-a-static-website-amazon-s3-cloudflare-127b57a13461)                 | Great guide to get you up and running                                                      |
| [Official Cloudflare Guide](https://support.cloudflare.com/hc/en-us/articles/360037983412-Configuring-an-Amazon-Web-Services-static-site-to-use-Cloudflare) | Detailed Cloudflare guide for Cloudflare and AWS hosting                                   |
| [jeff-h's StackOverflow answer](https://stackoverflow.com/a/70872265)                                                                                       | Explains Cloudflare Auto-minify setting to prevent broken CSS                              |
