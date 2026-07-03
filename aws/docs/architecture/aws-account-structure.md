# Aws Account Structure

**Repository:** `bfstore-platform-infra`  
**Status:** Draft v0.1  
**Last updated:** 2026-07-03

## Purpose

Document bfstore target AWS multi-account structure.

## Scope

Management, Security Tooling, Log Archive, Network, Shared Services, Dev, Stage, Prod and Sandbox accounts.

## bfstore position

bfstore uses a production-shaped AWS platform model: multi-account separation, federated workforce access, short-lived automation credentials, explicit workload identity, policy-as-code guardrails, central audit, and restore-tested backup strategies. The project deliberately self-manages selected platform components where that demonstrates operational competence, while documenting managed-service alternatives and trade-offs.

## Implementation guidance

- Use AWS Organizations with OUs for Security, Infrastructure, Workloads and Sandbox.
- Include a Network account from day one for contractor-level platform credibility.
- Keep Shared Services separate from Network.
- Keep Log Archive separate from Security Tooling.

## Required controls

- Management account must not run workloads.
- Network account must not host application workloads.
- All accounts inherit baseline logging and security controls.

## Validation and evidence

- Account structure documented before first environment build.
- OU/SCP design reviewed before attaching restrictive policies.



## References

- [AWS Organizations SCPs](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps.html)
- [AWS Security Reference Architecture](https://docs.aws.amazon.com/prescriptive-guidance/latest/security-reference-architecture/architecture.html)
