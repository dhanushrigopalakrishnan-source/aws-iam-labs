# Project 4: AWS Cross-Account IAM Role

## Objective

Configure an **AWS Cross-Account IAM Role** to allow an IAM user from one AWS account to securely access Amazon EC2 resources in another AWS account without sharing passwords or AWS access keys.

## Project Overview

In this project, I configured a cross-account IAM role that allows a user from one AWS account to access EC2 resources in another AWS account.

The role uses a **trust policy** to define which AWS account can assume the role and an **IAM permissions policy** to provide read-only access to Amazon EC2.

This demonstrates secure cross-account access using **AWS IAM Roles** and the **AWS Security Token Service (STS) AssumeRole** mechanism.

## AWS Services Used

* AWS IAM
* Amazon EC2
* AWS Security Token Service (STS)
* AWS Management Console

## AWS Account Configuration

Two AWS accounts were used for the cross-account access demonstration.

| Account | Purpose |
| ------- | ------- |
| Account A | Resource account |
| Account B | Trusted account |

### Account A

Account A contains the EC2 resources and the cross-account IAM role.

### Account B

Account B contains the IAM user that is allowed to assume the role.

## IAM Role Configuration

The following IAM role was created in Account A:

```text
CrossAccount-EC2-ReadOnly
