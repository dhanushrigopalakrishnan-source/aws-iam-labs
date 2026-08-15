
---

# Project 2 — Custom IAM Policy

```markdown
# Project 2: AWS Custom IAM Policy

## Objective

Create a **custom IAM policy** to provide specific permissions for Amazon EC2 actions while following the Principle of Least Privilege.

## Project Overview

In this project, I created a customer-managed IAM policy with specific EC2 permissions.

The policy was designed to allow required actions while preventing unauthorized actions such as terminating EC2 instances.

## AWS Services Used

* AWS IAM
* Amazon EC2
* AWS Management Console

## IAM Policy Configuration

The custom policy was configured to allow selected EC2 actions.

Example permissions included:

| EC2 Action | Permission |
|---|---|
| DescribeInstances | Allowed |
| RebootInstances | Allowed |
| TerminateInstances | Not Allowed |

## Architecture

```text
IAM User
    │
    ▼
Custom IAM Policy
    │
    ├── DescribeInstances → Allowed
    ├── RebootInstances   → Allowed
    └── TerminateInstances → Denied
