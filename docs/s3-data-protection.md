# S3 Data Protection

**Source:** Coursework-derived concepts with independent hardening  
**Status:** Complete design case study

## Scenario

A fictional application stores reports that must remain private, recoverable after accidental deletion, and auditable when accessed or changed.

## Control set

| Layer | Control | Security purpose |
|---|---|---|
| Exposure prevention | Account- and bucket-level Block Public Access | Prevent accidental public policies and ACLs |
| Authorization | Role-based bucket and object permissions | Limit access to approved workloads and responders |
| Encryption | Default server-side encryption | Protect stored objects and enforce an expected baseline |
| Recovery | Versioning with tested restore procedure | Recover overwritten or deleted objects |
| Monitoring | Management and appropriate data-event logging | Attribute policy and object activity |
| Retention | Lifecycle and retention decisions | Balance recovery, legal, and cost requirements |

## Validation

1. An approved workload role can write and read a fictional object.
2. An unauthenticated request is denied.
3. A read-only analyst cannot delete or alter the object.
4. A deleted object can be recovered from a prior version.
5. A bucket-policy change appears in the audit trail.
6. Routine operators cannot modify the protected audit-log destination.

## Misconfiguration analysis

Encryption does not correct public access, and Block Public Access does not correct an overprivileged internal role. Versioning improves recovery but can increase storage cost and does not replace an independent backup or retention policy. The controls are layered because each addresses a different failure mode.

## Cleanup

Versioned buckets require all object versions and delete markers to be handled before deletion. Test data, access points, replication rules, logging targets, and unused encryption keys must also be reviewed.
