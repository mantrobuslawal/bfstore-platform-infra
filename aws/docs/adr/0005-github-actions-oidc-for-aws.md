# Use GitHub Actions OIDC For AWS Access

**Status:** Proposed  
**Date:** 2026-07-03  
**Repository:** `bfstore-platform-infra`

## Context

bfstore is designed as a contractor-level AWS platform project. It needs a robust multi-account model, secure identity, auditable automation and infrastructure foundations that can evolve without migration chaos.

## Decision

bfstore will use GitHub OIDC and STS AssumeRoleWithWebIdentity instead of long-lived AWS access keys for CI/CD workflows.

## Rationale

- Shows production-shaped AWS platform judgement.
- Reduces reliance on manual console work and long-lived credentials.
- Keeps account ownership and blast-radius boundaries clear.
- Supports progressive enhancement without hiding learning value.

## Consequences

### Positive

- Clearer account ownership and stronger auditability.
- Better evidence for platform/DevSecOps contractor roles.
- Lower chance of retrofitting identity/network foundations later.

### Negative

- More upfront structure to understand and maintain.
- More documentation discipline required.

## Implementation notes

- Implement foundations first.
- Avoid overbuilding advanced services before core VPC, IAM, OpenTofu and GitOps foundations are stable.
- Capture deviations as follow-up ADRs.

## References

- [AWS Security Reference Architecture](https://docs.aws.amazon.com/prescriptive-guidance/latest/security-reference-architecture/architecture.html)
- [AWS Organizations SCPs](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps.html)
- [IAM roles](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html)
- [CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html)
