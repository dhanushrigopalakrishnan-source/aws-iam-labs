---

# Project 7 — IAM Policy Simulator

```markdown
# Project 7: AWS IAM Policy Simulator

## Objective

Use the **AWS IAM Policy Simulator** to test IAM permissions and verify whether specific AWS actions are allowed or denied.

## Project Overview

In this project, I created a custom IAM policy that provides limited EC2 permissions and used the IAM Policy Simulator to test the policy behavior.

The policy allowed EC2 instance description and reboot operations while preventing instance termination.

## AWS Services Used

* AWS IAM
* Amazon EC2
* IAM Policy Simulator
* AWS Management Console

## IAM Policy Configuration

The custom policy was:

```text
Project7-EC2-ReadReboot
