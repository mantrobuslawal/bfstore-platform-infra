# Account Access Model

**Repository:** `bfstore-platform-infra`  
**Status:** Draft v0.1  
**Last updated:** 2026-07-03

## Purpose

Define workforce access across bfstore AWS accounts.

## Scope

Management, security-tooling, log-archive, network, shared-services, dev, stage, prod and sandbox accounts.

## bfstore position

bfstore uses a production-shaped AWS platform model: multi-account separation, federated workforce access, short-lived automation credentials, explicit workload identity, policy-as-code guardrails, central audit, and restore-tested backup strategies. The project deliberately self-manages selected platform components where that demonstrates operational competence, while documenting managed-service alternatives and trade-offs.

## Implementation guidance

- Use IAM Identity Center groups as the source of workforce account access.
- Map groups to permission sets per account instead of creating IAM users.
- Give production read-only by default; use pipeline roles for planned changes.
- Keep management account access minimal and separate from workload administration.

## Required controls

- MFA required for all human access.
- Break-glass access is separate, monitored and tested.

## Validation and evidence

- Permission set/account matrix reviewed before environment creation.
- Quarterly review of IAM Identity Center assignments.



## References

- [IAM Identity Center permission sets](https://docs.aws.amazon.com/singlesignon/latest/userguide/permissionsets.html)
- [AWS Organizations SCPs](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps.html)
- [AWS Security Reference Architecture](https://docs.aws.amazon.com/prescriptive-guidance/latest/security-reference-architecture/architecture.html)
