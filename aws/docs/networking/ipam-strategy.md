# Ipam Strategy

**Repository:** `bfstore-platform-infra`  
**Status:** Draft v0.1  
**Last updated:** 2026-07-03

## Purpose

Define how bfstore moves from static CIDR planning to AWS VPC IPAM.

## Scope

Network architecture and implementation guidance for bfstore AWS accounts.

## bfstore position

bfstore uses a production-shaped AWS platform model: multi-account separation, federated workforce access, short-lived automation credentials, explicit workload identity, policy-as-code guardrails, central audit, and restore-tested backup strategies. The project deliberately self-manages selected platform components where that demonstrates operational competence, while documenting managed-service alternatives and trade-offs.

## Implementation guidance

- Keep IPAM ownership in the Network account.
- Define environment pools and future IPv6 pools.
- Avoid ad-hoc workload account CIDR allocation.

## Required controls

- Network changes are reviewed through PRs.
- Route/DNS changes include rollback notes.

## Validation and evidence

- Connectivity and non-connectivity tests recorded.



## References

- [AWS Security Reference Architecture](https://docs.aws.amazon.com/prescriptive-guidance/latest/security-reference-architecture/architecture.html)
