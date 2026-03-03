# EC2 → S3 Access Denied: IAM Policy Troubleshooting (Least Privilege Fix)

## Overview
This mini-lab demonstrates diagnosing and fixing an IAM permissions issue where an EC2 instance could not download an object from an S3 bucket using the AWS CLI. The solution uses a least-privilege, bucket-scoped custom policy attached to the instance role.

## Scenario
An EC2 instance needs to download an object from an S3 bucket:
- S3 bucket contains a test object (example: `test.txt`)
- EC2 uses an IAM role (instance profile) for AWS API permissions
- Initial download attempt fails due to missing S3 permissions

## Reproduction (CLI on the EC2 instance)
Attempt:
```bash
aws s3api get-object --bucket <BUCKET_NAME> --key test.txt my-test.txt
