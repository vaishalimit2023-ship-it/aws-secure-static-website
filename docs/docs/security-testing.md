# Security Testing Documentation

## 1. Objective
To verify that the static website is securely hosted using Amazon S3 and Amazon CloudFront.

## 2. Security Test Results

| Test Case | Expected Result | Actual Result |
|---|---|---|
| S3 Block Public Access | Public access blocked | Verified |
| Direct S3 website/object access | Access denied for anonymous users | AccessDenied |
| CloudFront website access | Website loads successfully over HTTPS | Passed |
| CloudFront Origin Access Control (OAC) | CloudFront can access private S3 objects | Passed |
| Website navigation | Navigation links open the correct sections | Passed |

## 3. Security Measures
- Amazon S3 Block Public Access is enabled.
- The S3 bucket is kept private.
- CloudFront uses Origin Access Control (OAC) to access S3 objects.
- The S3 bucket policy grants access to the configured CloudFront distribution.
- HTTPS is used to access the website through CloudFront.
- AWS credentials and secret keys are not stored in the GitHub repository.

## 4. Conclusion
The security checks indicate that the website is accessible through CloudFront while direct anonymous access to the private S3 origin is denied.

## 5. Future Improvements
- Configure AWS CloudTrail for auditing.
- Add monitoring and alerts.
- Automate deployment using GitHub Actions.
- Manage infrastructure using AWS CloudFormation.
