# Iam Policy Testing

**Repository:** `bfstore-platform-infra`  
**Status:** Draft v0.1  
**Last updated:** 2026-07-03

## Purpose

Set the testing approach for IAM policies.

## Scope

Static validation, Access Analyzer, policy simulation, negative testing, CloudTrail review and OPA/Rego checks.

## bfstore position

bfstore uses a production-shaped AWS platform model: multi-account separation, federated workforce access, short-lived automation credentials, explicit workload identity, policy-as-code guardrails, central audit, and restore-tested backup strategies. The project deliberately self-manages selected platform components where that demonstrates operational competence, while documenting managed-service alternatives and trade-offs.

## Implementation guidance

- Validate IAM JSON and policy findings before merge.
- Use IAM Access Analyzer for external access, unused access and policy issues.
- Add negative tests for unauthorised repo, branch, account and tag conditions.
- Use OPA/Rego checks for high-risk OpenTofu plans.

## Required controls

- No IAM policy merged without review.
- No KMS key policy change without explicit review.

## Validation and evidence

- Access Analyzer output attached to PR or stored as evidence.
- Sandbox/policy simulation recorded for privileged changes.



## References

- [IAM Access Analyzer](https://docs.aws.amazon.com/IAM/latest/UserGuide/what-is-access-analyzer.html)
- [IAM JSON policy reference](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies.html)
- [SCP examples](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps_examples.html)
