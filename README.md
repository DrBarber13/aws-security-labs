# AWS Security Labs

**Status:** Coursework analyzed; independent cloud rebuild planned  
**Project source:** Coursework-derived concepts with independent security extensions

## Overview

This repository turns AWS coursework into original, security-focused case studies. Examples must use fictitious account IDs, resource names, IP ranges, and sanitized screenshots.

## Lab roadmap

| Lab | Security focus | Source | Status |
|---|---|---|---|
| [Secure AWS foundation](docs/secure-aws-foundation.md) | IAM, VPC, EC2, S3, RDS, scaling | Coursework-derived | Case study complete; rebuild pending |
| IAM least privilege | Users, roles, policies, MFA | Coursework-derived + independent hardening | Rebuild planned |
| Secure VPC | Segmentation, routing, security groups | Coursework-derived | Rebuild planned |
| S3 data protection | Block Public Access, encryption, logging | Coursework-derived + independent hardening | Rebuild planned |
| CloudTrail investigation | Audit evidence and event review | Independent extension | Planned |
| GuardDuty triage | Findings and response workflow | Independent extension | Planned |

## Recommended evidence

- Original architecture diagrams
- Redacted policy snippets with explanations
- Validation commands with fake account values
- Screenshots with account number, ARN details, email, IP, and access keys removed
- Cost-control and cleanup notes

## Skills demonstrated

AWS IAM, VPC, S3, CloudTrail, GuardDuty, least privilege, logging, cloud investigation, documentation.

## Security rules

Never commit access keys, session tokens, `.env` files, Terraform state, credentials, account IDs, or copied course instructions.
