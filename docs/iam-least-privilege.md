# IAM Least-Privilege Design

**Source:** Coursework-derived concepts with independent hardening  
**Status:** Complete design case study

## Scenario

A fictional operations team needs to view inventory and troubleshoot a web workload without receiving permission to alter identity controls, delete data, or disable logging.

## Design decisions

- Workforce access is federated; long-lived IAM user keys are avoided.
- Job functions map to roles rather than permissions attached directly to people.
- Administrative access requires MFA and a separate privileged role.
- Resource-level permissions are used when the service supports them.
- Explicit denies protect logging and recovery resources from routine roles.
- Temporary elevation has an owner, justification, and expiration.

## Example policy pattern

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "ReadApprovedInventory",
      "Effect": "Allow",
      "Action": [
        "ec2:Describe*",
        "s3:ListAllMyBuckets",
        "cloudwatch:GetMetricData"
      ],
      "Resource": "*"
    },
    {
      "Sid": "DenyAuditDisruption",
      "Effect": "Deny",
      "Action": [
        "cloudtrail:StopLogging",
        "cloudtrail:DeleteTrail"
      ],
      "Resource": "*"
    }
  ]
}
```

The wildcard resource is limited to read-only APIs that do not support narrower resource scoping in the same way as data-plane actions. Production policies still require service-specific review.

## Validation

| Attempt | Expected result |
|---|---|
| Describe compute instances | Allowed |
| Read approved monitoring metrics | Allowed |
| Launch or terminate an instance | Denied |
| Change another identity's policy | Denied |
| Stop or delete an audit trail | Explicitly denied |

## Residual risk

Read access can still reveal sensitive metadata. Least privilege must therefore be combined with data classification, session logging, access review, and careful control of role-assumption paths.
