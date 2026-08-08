# Project 1 – IAM Users and Groups

## Objective

Create IAM users and groups for different departments and assign permissions using IAM groups.

## AWS Services Used

- AWS IAM
- Amazon EC2
- Amazon RDS
- Amazon CloudWatch

## IAM Groups

| Group | Policy |
|---|---|
| Developers | AmazonEC2ReadOnlyAccess |
| DBAdmins | AmazonRDSFullAccess |
| Support | CloudWatchReadOnlyAccess |

## Users

| User | Group |
|---|---|
| dev1 | Developers |
| dev2 | Developers |
| dba1 | DBAdmins |
| support1 | Support |

## Permission Testing

The `dev1` user was given `AmazonEC2ReadOnlyAccess`.

### Test Result

- View EC2 resources: ✅ Allowed
- Terminate EC2 instance: ❌ Denied

The termination attempt resulted in an authorization error because the user did not have the `ec2:TerminateInstances` permission.

## Security Concepts

- IAM Users
- IAM Groups
- AWS Managed Policies
- Principle of Least Privilege

## Learning Outcome

Learned how to create IAM users and groups and control AWS resource access using group-based permissions.
