# Break Glass Access

**Repository:** `bfstore-platform-infra`  
**Status:** Draft v0.1  
**Last updated:** 2026-07-03

## Purpose

Define emergency access for bfstore.

## Scope

Break-glass roles, MFA, approval, session duration, alerting, permitted use cases and post-use review.

## bfstore position

bfstore uses a production-shaped AWS platform model: multi-account separation, federated workforce access, short-lived automation credentials, explicit workload identity, policy-as-code guardrails, central audit, and restore-tested backup strategies. The project deliberately self-manages selected platform components where that demonstrates operational competence, while documenting managed-service alternatives and trade-offs.

## Implementation guidance

- Break-glass is exceptional, not a shortcut around normal delivery.
- Use obvious emergency role names in logs.
- Require MFA and short session duration.
- Create an incident note every time break-glass is used.

## Required controls

- No break-glass access without monitoring.
- All emergency changes must be reconciled back into OpenTofu/GitOps.

## Validation and evidence

- Test break-glass quarterly in a controlled scenario.
- Verify CloudTrail and alerting fire on use.



## References

- [CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html)
- [IAM roles](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html)
- [IAM Identity Center permission sets](https://docs.aws.amazon.com/singlesignon/latest/userguide/permissionsets.html)
