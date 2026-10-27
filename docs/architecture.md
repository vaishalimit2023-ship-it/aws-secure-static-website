# AWS Architecture Documentation

## Project Overview

**Project:** Secure Static Website Hosting on AWS using Amazon S3 and Amazon CloudFront.

This project hosts a static portfolio website using a private Amazon S3 bucket and delivers it through Amazon CloudFront.

## Architecture Diagram

```text
                 Website Visitor
                       |
                       | HTTPS
                       v
                Amazon CloudFront
                       |
                       | Origin Access Control (OAC)
                       v
                Private Amazon S3
                       |
                       v
               Index.html + Style.css
```

## AWS Components

### 1. Amazon S3
- Stores the website's HTML and CSS files.
- Block Public Access remains enabled.
- Direct anonymous access to the S3 object was tested and returned `AccessDenied`.

### 2. Amazon CloudFront
- Distributes the website content to visitors.
- Provides HTTPS access to the website.
- Supports cache invalidation when website files are updated.

### 3. Origin Access Control (OAC)
- Allows the configured CloudFront distribution to access the private S3 origin.
- Works with the S3 bucket policy to restrict origin access.

### 4. Website Files
- `Index.html` — page structure and content.
- `Style.css` — layout, colors and responsive styling.

## Security Design

- S3 Block Public Access is enabled.
- CloudFront uses OAC to access the private S3 bucket.
- Visitors access the website through the CloudFront HTTPS URL.
- AWS credentials and secret keys must never be committed to GitHub.

## Verification Results

| Test | Result |
|---|---|
| Direct S3 object URL | `AccessDenied` |
| CloudFront website | Working |
| Navigation links | Working |

## Future Improvements

- AWS CloudFormation infrastructure template.
- GitHub Actions CI/CD deployment.
- Additional security tests and monitoring.
