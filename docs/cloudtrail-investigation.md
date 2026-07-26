# CloudTrail Investigation: Unexpected Policy Change

**Source:** Independent tabletop exercise  
**Status:** Complete case study  
**Disposition:** Suspicious until authorization is established

## Alert

An identity policy was changed outside the normal maintenance window. The investigation must identify the actor, authentication path, affected policy, resulting permissions, and follow-on activity.

## Timeline

| Relative time | Event | Interpretation |
|---|---|---|
| T-8 min | Federated console session begins | Establishes the session under review |
| T0 | Policy version is created | Primary configuration change |
| T+1 min | New policy version becomes default | Permissions may now differ |
| T+5 min | Resource inventory calls increase | Could be validation or discovery |
| T+18 min | Change owner cannot identify an approved request | Escalates suspicion |

## Triage fields

- event source and event name;
- event time and region;
- user identity type, principal, and session issuer;
- source address and user agent;
- request parameters and affected resource;
- response errors;
- MFA and role-assumption context; and
- related events sharing the principal, source, or session.

## Response decision

If the change is unauthorized:

1. preserve the relevant audit records;
2. disable or restrict the compromised access path;
3. revert the policy to the last reviewed version;
4. revoke active sessions where supported;
5. review actions performed under the resulting permissions;
6. rotate exposed credentials if credential compromise is plausible; and
7. document the timeline, impact, and confidence.

## Detection logic

Prioritize changes to identity policies, trust policies, audit trails, log-bucket controls, security groups, and authentication devices. Increase severity when the actor is new, MFA is absent, the source is unusual, or the change is followed by enumeration or credential activity.

## Limitations

CloudTrail shows API activity, not human intent. Authorization requires correlation with identity-provider records, change management, asset ownership, and other telemetry.
