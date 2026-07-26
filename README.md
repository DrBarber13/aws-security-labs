# AWS Security Labs

**Status:** Six sanitized cloud-security case studies complete  
**Project source:** Coursework-derived concepts with independent security extensions

## Overview

This repository turns AWS coursework into original, security-focused case studies. Examples must use fictitious account IDs, resource names, IP ranges, and sanitized screenshots.

## Lab roadmap

| Lab | Security focus | Source | Status |
|---|---|---|---|
| [Secure AWS foundation](docs/secure-aws-foundation.md) | IAM, VPC, EC2, S3, RDS, scaling | Coursework-derived | Complete case study |
| [IAM least privilege](docs/iam-least-privilege.md) | Roles, policies, MFA, permission boundaries | Coursework-derived + independent hardening | Complete design |
| [Secure VPC](docs/secure-vpc.md) | Segmentation, routing, security groups, flow logs | Coursework-derived | Complete design |
| [S3 data protection](docs/s3-data-protection.md) | Public-access prevention, encryption, versioning | Coursework-derived + independent hardening | Complete design |
| [CloudTrail investigation](docs/cloudtrail-investigation.md) | Audit timeline and containment | Independent tabletop exercise | Complete case study |
| [GuardDuty triage](docs/guardduty-triage.md) | Finding enrichment and response workflow | Independent tabletop exercise | Complete case study |

## Evidence represented

- Original Mermaid architecture diagrams
- Least-privilege policy patterns with explanations
- Positive and negative validation tests using fictional resources
- Investigation timelines and response decision points
- Cost-control and cleanup considerations

## Skills demonstrated

AWS IAM, VPC, S3, CloudTrail, GuardDuty, least privilege, logging, cloud investigation, documentation.

## Security rules

Never commit access keys, session tokens, `.env` files, Terraform state, credentials, account IDs, or copied course instructions.
