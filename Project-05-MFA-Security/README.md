# Project 5: AWS IAM MFA Security

## Objective

Configure **Multi-Factor Authentication (MFA)** for an AWS IAM user to improve account security.

## Project Overview

In this project, I enabled a **Virtual MFA device** for an AWS IAM user.

MFA provides an additional security layer by requiring both a password and an MFA verification code.

## AWS Services Used

* AWS IAM
* AWS Management Console

## MFA Configuration

A Virtual MFA device was configured for the IAM user:

**MFAUser**

| Setting | Configuration |
|---|---|
| MFA Type | Virtual MFA Device |
| IAM User | MFAUser |
| MFA Status | Enabled |

## Architecture

```text
IAM User
    |
    +----------------+
    |                |
    v                v
 Password         MFA Code
    |                |
    +-------+--------+
            |
            v
      AWS Authentication
            |
            v
