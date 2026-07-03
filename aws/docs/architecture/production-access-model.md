# Production Access Model

**Repository:** `bfstore-platform-infra`  
**Status:** Draft v0.1  
**Last updated:** 2026-07-03

## Purpose

Define how bfstore production access is granted, used and audited.

## Scope

Human access, CI/CD access, break-glass, workload identity, observability access and database/secrets access.

## bfstore position

bfstore uses a production-shaped AWS platform model: multi-account separation, federated workforce access, short-lived automation credentials, explicit workload identity, policy-as-code guardrails, central audit, and restore-tested backup strategies. The project deliberately self-manages selected platform components where that demonstrates operational competence, while documenting managed-service alternatives and trade-offs.

## Implementation guidance

- Production human access is read-only by default.
- Planned production changes go through OIDC-backed automation with approval gates.
- Application workloads receive only per-service AWS permissions.
- Central observability control plane lives outside prod.

## Required controls

- No shared admin credentials.
- No static keys for production automation.
- All privileged paths logged.

## Validation and evidence

- Production change path tested in stage first.
- CloudTrail role assumption reports reviewed.



## References

- [CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html)
- [IAM Access Analyzer](https://docs.aws.amazon.com/IAM/latest/UserGuide/what-is-access-analyzer.html)
- [IAM roles](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html)
