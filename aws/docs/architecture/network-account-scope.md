# Network Account Scope

**Repository:** `bfstore-platform-infra`  
**Status:** Draft v0.1  
**Last updated:** 2026-07-03

## Purpose

Define the scope and responsibilities of the bfstore Network account.

## Scope

Central CIDR/IPAM strategy, Transit Gateway, network guardrails, DNS/resolver strategy, future central egress and inspection.

## bfstore position

bfstore uses a production-shaped AWS platform model: multi-account separation, federated workforce access, short-lived automation credentials, explicit workload identity, policy-as-code guardrails, central audit, and restore-tested backup strategies. The project deliberately self-manages selected platform components where that demonstrates operational competence, while documenting managed-service alternatives and trade-offs.

## Implementation guidance

- Create Network account under Infrastructure OU from day one.
- Implement a thin foundation first: account baseline, IAM, logging, guardrails and CIDR strategy.
- Use the account as owner of central routing/address allocation, not workloads.
- Plan Transit Gateway explicitly; defer central egress/inspection until foundations are stable.

## Required controls

- Network changes require PR review and audit.
- CIDR allocations must be non-overlapping and documented.

## Validation and evidence

- CIDR plan reviewed for overlap before VPC creation.
- TGW route changes tested in dev/shared-services before stage/prod.



## References

- [AWS Security Reference Architecture](https://docs.aws.amazon.com/prescriptive-guidance/latest/security-reference-architecture/architecture.html)
- [AWS Organizations SCPs](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps.html)
- [CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html)
