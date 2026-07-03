# Cidr Allocation Strategy

**Repository:** `bfstore-platform-infra`  
**Status:** Draft v0.1  
**Last updated:** 2026-07-03

## Purpose

Define bfstore non-overlapping IPv4 CIDR plan across accounts/environments.

## Scope

Network architecture and implementation guidance for bfstore AWS accounts.

## bfstore position

bfstore uses a production-shaped AWS platform model: multi-account separation, federated workforce access, short-lived automation credentials, explicit workload identity, policy-as-code guardrails, central audit, and restore-tested backup strategies. The project deliberately self-manages selected platform components where that demonstrates operational competence, while documenting managed-service alternatives and trade-offs.

## Implementation guidance

- Maintain a documented static CIDR map first.
- Reserve ranges for shared-services, network, dev, stage, prod, security and sandbox.
- Move to IPAM when the platform matures.

## Required controls

- Network changes are reviewed through PRs.
- Route/DNS changes include rollback notes.

## Validation and evidence

- Connectivity and non-connectivity tests recorded.



## References

- [AWS Security Reference Architecture](https://docs.aws.amazon.com/prescriptive-guidance/latest/security-reference-architecture/architecture.html)
