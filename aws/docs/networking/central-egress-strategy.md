# Central Egress Strategy

**Repository:** `bfstore-platform-infra`  
**Status:** Draft v0.1  
**Last updated:** 2026-07-03

## Purpose

Document the future central egress pattern.

## Scope

Network architecture and implementation guidance for bfstore AWS accounts.

## bfstore position

bfstore uses a production-shaped AWS platform model: multi-account separation, federated workforce access, short-lived automation credentials, explicit workload identity, policy-as-code guardrails, central audit, and restore-tested backup strategies. The project deliberately self-manages selected platform components where that demonstrates operational competence, while documenting managed-service alternatives and trade-offs.

## Implementation guidance

- Defer central egress until multiple VPCs justify it.
- Keep local NAT/VPC endpoints acceptable in v1.
- Model future egress through Network account with firewall/inspection.

## Required controls

- Network changes are reviewed through PRs.
- Route/DNS changes include rollback notes.

## Validation and evidence

- Connectivity and non-connectivity tests recorded.



## References

- [AWS Security Reference Architecture](https://docs.aws.amazon.com/prescriptive-guidance/latest/security-reference-architecture/architecture.html)
