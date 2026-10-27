# Secure Static Website Hosting on AWS

A professional static portfolio website hosted on Amazon S3 and delivered through Amazon CloudFront, with private origin access and HTTPS.

## Live Demo

**Website:** https://d1e7a1wc0lszas.cloudfront.net

## Project Overview

This project demonstrates how to host and deliver a static website using AWS cloud services. The website uses a responsive dark-themed design built with HTML and CSS.

## AWS Services Used

- **Amazon S3** — Stores website files in a private bucket.
- **Amazon CloudFront** — Delivers website content to users over HTTPS.
- **Origin Access Control (OAC)** — Allows CloudFront to access the private S3 origin without making the bucket public.

## Architecture

User → Amazon CloudFront (HTTPS) → Private Amazon S3 bucket

CloudFront accesses the S3 origin using OAC. Public access to the S3 bucket remains blocked.

## Features

- Responsive portfolio website
- Dark navy theme with blue highlights
- About, Skills, Projects and Contact sections
- Private S3 bucket
- CloudFront content delivery
- HTTPS access
- CloudFront cache invalidation for updated website files

## Repository Structure

```text
aws-secure-static-website/
├── Index.html
├── Style.css
└── README.md
```

The website files are stored at the repository root in this initial version. They can be moved into a `website/` folder as the project grows.

## Security Verification

- Direct anonymous access to the S3 object URL returned `AccessDenied`.
- The website was accessible through the CloudFront distribution.
- S3 Block Public Access remains enabled.
- CloudFront OAC is configured for private origin access.

## Future Improvements

- Infrastructure as Code using AWS CloudFormation
- Automated deployment using GitHub Actions
- Automated CloudFront cache invalidation
- Architecture diagram and additional test documentation
- Monitoring and logging improvements

## Skills Demonstrated

Amazon S3, Amazon CloudFront, Origin Access Control, HTTPS, HTML, CSS and cloud security fundamentals.

## Disclaimer

This is a learning and portfolio project. AWS resource usage may incur charges depending on configuration and usage. Review AWS pricing and remove resources that are no longer needed.

##  Documentation

- [Architecture Documentation](docs/architecture.md)
- [Security Testing Documentation](docs/security-testing.md)

##  Live Website

[View MyCloud Portfolio](https://d1e7a1wc0lszas.cloudfront.net)
