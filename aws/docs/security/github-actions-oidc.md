# Github Actions Oidc

**Repository:** `bfstore-platform-infra`  
**Status:** Draft v0.1  
**Last updated:** 2026-07-03

## Purpose

Define how GitHub Actions obtains short-lived AWS credentials for bfstore.

## Scope

OIDC providers, STS role assumption, trust policies, branch/environment conditions, plan/apply separation and audit.

## bfstore position

bfstore uses a production-shaped AWS platform model: multi-account separation, federated workforce access, short-lived automation credentials, explicit workload identity, policy-as-code guardrails, central audit, and restore-tested backup strategies. The project deliberately self-manages selected platform components where that demonstrates operational competence, while documenting managed-service alternatives and trade-offs.

## Implementation guidance

- Create one OIDC provider per AWS account where GitHub workflows need roles.
- Separate `plan` and `apply` roles.
- Restrict trust policies to expected GitHub organisation/repository/branch/environment.
- Use GitHub protected environments for stage/prod applies.

## Required controls

- No AWS access key secrets for normal GitHub workflows.
- Production apply roles require protected branch and environment approval.

## Validation and evidence

- Test OIDC assumption from allowed and denied branches.
- Review CloudTrail events for `AssumeRoleWithWebIdentity`.



## References

- [IAM roles](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html)
- [CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html)
