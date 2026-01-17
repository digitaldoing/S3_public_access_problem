# AWS Public Access Problem

## The Problem
A public cloud solutions site (FlameOnePage) has experienced downtime when images stored in an AWS S3 static website configuration have become inaccessible due to misconfigured bucket permissions.

## Investigation Process (things checked/verified)
- Reproduced the Access Denied issue.
- Reviewed S3 public access settings.
- Compared IAM roles and bucket policies.

## Problems encountered
During testing I added a Get Object policy for an IAM user who had programmatic access to the AWS CLI. I was initially under the impression that the policy would allow access to the static website bucket via the AWS console allowing them to upload additional objects. Upon further testing, the user could only securely upload new objects into the bucket using the AWS CLI with no access permitted via the AWS console.

## Solution
Implemented a least-privilege S3 bucket policy allowing controlled public object access.

[Video showing my implented solution here](https://youtu.be/ki520u4xcWY)


## Validation
- Tested object URLs in a browser, verified public access.
- Confirmed no unauthorized uploads possible.

## Result
✅ Product images restored.
✅ Permissions secured.
✅ Cost: $0 (AWS Free Tier).

## Skills Highlighted
AWS S3 • IAM • Cloud Security • Troubleshooting • Documentation
