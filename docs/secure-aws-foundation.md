# Secure AWS Foundation

**Source:** Coursework-derived case study, independently rewritten  
**Status:** Skills documented; independent account revalidation and sanitized evidence pending

## Scenario

A fictional web workload needs a cloud foundation that separates public and private resources, limits identity permissions, protects stored data, supports recovery, and scales under changing demand.

The reviewed coursework included AWS IAM, VPC and subnet construction, web-server deployment, EC2, Lambda, Elastic Beanstalk, EBS, S3, RDS, load balancing, Auto Scaling, and monitoring. Original lab instructions, validation screens, account values, and student-named resources remain private.

## Identity and access management

The IAM exercise demonstrated group-based permission assignment and the practical effect of read-only access. A user inherited permissions through group membership and could view S3 resources without modifying or deleting objects.

The independent rebuild will extend this foundation by:

- Using roles instead of long-lived user access keys where possible
- Requiring MFA for privileged access
- Scoping policies to specific actions and resources
- Reviewing unused identities and permissions
- Recording administrative activity through CloudTrail

## Network design

The VPC work covered multiple subnets, availability zones, security groups, and a web workload. The public version will use a new architecture diagram and documentation-safe values.

Planned security controls include:

- Public subnets only for internet-facing load-balancing components
- Private subnets for application and database tiers
- Restrictive security-group references between tiers
- No direct public database exposure
- VPC flow logging for investigation support

## Data protection

The coursework distinguished S3 object storage from EBS block storage and demonstrated S3 permissions, object access, bucket policy behavior, and versioning.

The independent rebuild will validate:

- S3 Block Public Access
- Default encryption
- Versioning and recovery of a deleted test object
- Least-privilege bucket access
- Lifecycle and retention decisions
- RDS placement and encrypted storage

## Availability and monitoring

The reviewed work included load balancer configuration, launch templates or configurations, Auto Scaling, and predictive monitoring concepts. These components support availability, but they do not replace backup or incident detection.

The rebuild will add:

- Health checks and scaling validation
- CloudWatch metrics and alarms
- CloudTrail event review
- Cost controls and resource cleanup

## Validation plan

1. Confirm a read-only identity can list approved resources but cannot modify them.
2. Verify private workloads cannot be reached directly from the internet.
3. Test application reachability only through the intended entry point.
4. Delete and restore a versioned test object.
5. Confirm audit events appear for administrative actions.
6. Remove all billable resources after testing.

## Skills demonstrated

AWS IAM, least privilege, VPC architecture, subnets, security groups, EC2, S3, EBS, RDS, load balancing, Auto Scaling, CloudWatch, resilience, and technical documentation.

## Publication safeguards

No account IDs, ARNs, access keys, student identifiers, resource names, lab-provider content, or original screenshots are included. The public evidence set will be recreated in an authorized environment.
