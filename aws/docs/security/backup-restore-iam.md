# Backup Restore Iam

**Repository:** `bfstore-platform-infra`  
**Status:** Draft v0.1  
**Last updated:** 2026-07-03

## Purpose

Define IAM requirements for backup and restore workflows.

## Scope

OpenTofu state, data stores, logs, secrets and platform tooling backups.

## bfstore position

bfstore uses a production-shaped AWS platform model: multi-account separation, federated workforce access, short-lived automation credentials, explicit workload identity, policy-as-code guardrails, central audit, and restore-tested backup strategies. The project deliberately self-manages selected platform components where that demonstrates operational competence, while documenting managed-service alternatives and trade-offs.

## Implementation guidance

- Create separate roles for backup creation and restore testing where possible.
- Grant restore-test roles access to isolated environments, not production by default.
- KMS key policies must allow required backup and restore operations.
- OpenTofu state and MySQL/database backups must be restore-tested.

## Required controls

- A backup is not valid until restore has been tested.
- Backup deletion is more restricted than backup creation.

## Validation and evidence

- Run scheduled restore tests for OpenTofu state and database backups.
- Record restore duration, validation checks and cleanup.



## References

- [AWS Backup service roles](https://docs.aws.amazon.com/aws-backup/latest/devguide/iam-service-roles.html)
- [KMS key policies](https://docs.aws.amazon.com/kms/latest/developerguide/key-policies.html)
- [CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html)
