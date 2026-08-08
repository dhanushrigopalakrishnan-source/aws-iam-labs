# Project 2 – Custom IAM Policy

## Objective

Create a customer managed IAM policy that allows a user to start, stop, reboot, and view EC2 instances, while preventing the user from terminating instances.

## AWS Services Used

- AWS IAM
- Amazon EC2

## IAM User

`ec2-operator`

## Custom Policy

Policy name:

`EC2StartStopRebootOnly`

## Permissions

| EC2 Action | Permission |
|---|---|
| Describe instances | ✅ Allowed |
| Start instance | ✅ Allowed |
| Stop instance | ✅ Allowed |
| Reboot instance | ✅ Allowed |
| Terminate instance | ❌ Denied |

## Policy JSON

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "ec2:StartInstances",
        "ec2:StopInstances",
        "ec2:RebootInstances",
        "ec2:DescribeInstances"
      ],
      "Resource": "*"
    }
  ]
}
