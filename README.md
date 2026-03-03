# EC2 → S3 Access Denied: IAM Policy Troubleshooting (Least Privilege Fix)

## Overview
This project demonstrates diagnosing and resolving an IAM permissions issue where an EC2 instance could not retrieve an object from an S3 bucket using the AWS CLI. The solution implements a least-privilege, bucket-scoped IAM policy instead of using a broad managed policy.

---

## Scenario
An EC2 instance needs to download an object from an S3 bucket:

- S3 bucket contains a test object (example: `test.txt`)
- EC2 uses an IAM role (instance profile) for AWS API permissions
- Network configuration is correct
- Initial download attempt fails

---

## Reproduction (CLI on the EC2 instance)

Attempt:

```bash
aws s3api get-object --bucket <BUCKET_NAME> --key test.txt my-test.txt
