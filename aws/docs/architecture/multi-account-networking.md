# Multi Account Networking

**Repository:** `bfstore-platform-infra`  
**Status:** Draft v0.1  
**Last updated:** 2026-07-03

## Purpose

Explain bfstore phased multi-account networking strategy.

## Scope

Standalone VPCs, shared-services connectivity, Transit Gateway, egress/inspection, DNS and future IPAM/IPv6.

## bfstore position

bfstore uses a production-shaped AWS platform model: multi-account separation, federated workforce access, short-lived automation credentials, explicit workload identity, policy-as-code guardrails, central audit, and restore-tested backup strategies. The project deliberately self-manages selected platform components where that demonstrates operational competence, while documenting managed-service alternatives and trade-offs.

## Implementation guidance

- Begin with non-overlapping VPC CIDRs per account.
- Use Network account for central routing strategy.
- Attach dev and shared-services first when testing Transit Gateway.
- Attach prod after route tables and controls are proven.

## Required controls

- No overlapping VPC CIDRs.
- No implicit all-to-all environment routing.

## Validation and evidence

- Document intended route tables and traffic paths.
- Test connectivity and non-connectivity.



## References

- [AWS Security Reference Architecture](https://docs.aws.amazon.com/prescriptive-guidance/latest/security-reference-architecture/architecture.html)
