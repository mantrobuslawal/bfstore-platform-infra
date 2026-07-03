# Shared Services Account

**Repository:** `bfstore-platform-infra`  
**Status:** Draft v0.1  
**Last updated:** 2026-07-03

## Purpose

Define the scope of the bfstore Shared Services account.

## Scope

TerraKube, observability tooling, internal registries, GitOps/control-plane services and future platform tools.

## bfstore position

bfstore uses a production-shaped AWS platform model: multi-account separation, federated workforce access, short-lived automation credentials, explicit workload identity, policy-as-code guardrails, central audit, and restore-tested backup strategies. The project deliberately self-manages selected platform components where that demonstrates operational competence, while documenting managed-service alternatives and trade-offs.

## Implementation guidance

- Use Shared Services for platform capabilities consumed by other accounts.
- Candidate services include TerraKube, central observability, private registry and GitOps tooling.
- Do not place production application workloads in Shared Services.

## Required controls

- Tooling that can change infrastructure is production-sensitive.
- Backup and restore must cover TerraKube/database/state, registry data and dashboards.

## Validation and evidence

- Cross-account role assumptions logged and reviewed.
- Restore tests run for shared tooling state.



## References

- [AWS Security Reference Architecture](https://docs.aws.amazon.com/prescriptive-guidance/latest/security-reference-architecture/architecture.html)
- [IAM roles](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html)
- [CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html)
