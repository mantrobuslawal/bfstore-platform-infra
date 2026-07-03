# Shared Services Vs Network Account

**Repository:** `bfstore-platform-infra`  
**Status:** Draft v0.1  
**Last updated:** 2026-07-03

## Purpose

Clarify Shared Services versus Network account boundaries.

## Scope

Which capabilities belong in each account and how they interact.

## bfstore position

bfstore uses a production-shaped AWS platform model: multi-account separation, federated workforce access, short-lived automation credentials, explicit workload identity, policy-as-code guardrails, central audit, and restore-tested backup strategies. The project deliberately self-manages selected platform components where that demonstrates operational competence, while documenting managed-service alternatives and trade-offs.

## Implementation guidance

- Shared Services owns platform tools: TerraKube, observability, registries and GitOps.
- Network owns packet movement: Transit Gateway, central egress, inspection, IPAM and DNS resolver strategy.
- Do not combine them just because both are infrastructure-shaped.

## Required controls

- Network account must not become a tooling dumping ground.
- Shared Services must not own central routing authority.

## Validation and evidence

- Account responsibility matrix reviewed.
- ADR links maintained between tooling and networking decisions.



## References

- [AWS Security Reference Architecture](https://docs.aws.amazon.com/prescriptive-guidance/latest/security-reference-architecture/architecture.html)
