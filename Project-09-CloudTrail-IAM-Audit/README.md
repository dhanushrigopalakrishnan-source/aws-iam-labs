# Project 9 – CloudTrail IAM Audit

## Objective

To understand how AWS CloudTrail records and provides visibility into API activity performed within an AWS account.

This project demonstrates how CloudTrail can be used to identify:

- Who performed an AWS API request
- Which AWS service was accessed
- What action was requested
- When the request occurred
- The AWS Region
- Whether the request was successful or resulted in an error

## AWS Services Used

- AWS CloudTrail
- Amazon EC2
- AWS IAM

## CloudTrail Event History

AWS CloudTrail Event History was used to inspect a recorded EC2 API event.

### Event Details

| Attribute | Value |
|---|---|
| Event Name | `CreateKeyPair` |
| User | `student1` |
| Event Source | `ec2.amazonaws.com` |
| AWS Region | `eu-north-1` |
| Read-only | `false` |
| Result | `Client.UnauthorizedOperation` |

The event was recorded even though the API request was unsuccessful.

This demonstrates that CloudTrail can provide an audit trail of AWS API requests, including unsuccessful requests.

## Audit Flow

```text
IAM User
    |
    v
AWS API Request
    |
    v
Amazon EC2
    |
    v
AWS CloudTrail
    |
    v
Event History
    |
    v
Audit Information
