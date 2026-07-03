# Iam Operating Model

**Repository:** `bfstore-platform-infra`  
**Status:** Draft v0.1  
**Last updated:** 2026-07-03

## Purpose

Describe how IAM is operated day-to-day across bfstore.

## Scope

Role ownership, access requests, approval, implementation, review and retirement.

## bfstore position

bfstore uses a production-shaped AWS platform model: multi-account separation, federated workforce access, short-lived automation credentials, explicit workload identity, policy-as-code guardrails, central audit, and restore-tested backup strategies. The project deliberately self-manages selected platform components where that demonstrates operational competence, while documenting managed-service alternatives and trade-offs.

## Implementation guidance

- All access changes move through pull requests unless emergency access is required.
- IAM changes include reason, blast-radius notes, target accounts/resources and rollback plan.
- Production access is time-bound or review-bound; avoid standing broad permissions.
- Use permissions boundaries for automation-created roles where privilege expansion risk exists.

## Required controls

- No unaudited manual production IAM change.
- No wildcard `iam:PassRole` except documented temporary bootstrap exception.

## Validation and evidence

- Pull request checklist completed for each IAM change.
- Access Analyzer findings triaged after IAM releases.



## References

- [IAM roles](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html)
- [IAM Access Analyzer](https://docs.aws.amazon.com/IAM/latest/UserGuide/what-is-access-analyzer.html)
- [CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html)
