# Identity And Access Management

**Repository:** `bfstore-platform-infra`  
**Status:** Draft v0.1  
**Last updated:** 2026-07-03

## Purpose

Define bfstore AWS identity and access management across people, pipelines, workloads, services and accounts.

## Scope

IAM, IAM Identity Center, AWS Organizations, STS, OIDC, EKS workload identity, KMS access, CloudTrail auditability and least-privilege iteration.

## bfstore position

bfstore uses a production-shaped AWS platform model: multi-account separation, federated workforce access, short-lived automation credentials, explicit workload identity, policy-as-code guardrails, central audit, and restore-tested backup strategies. The project deliberately self-manages selected platform components where that demonstrates operational competence, while documenting managed-service alternatives and trade-offs.

## Implementation guidance

- Use IAM Identity Center for workforce access; avoid daily-use IAM users.
- Use IAM roles and STS temporary credentials for humans, CI/CD and workloads.
- Use GitHub Actions OIDC for OpenTofu and service deployment pipelines.
- Use EKS Pod Identity or IRSA for Kubernetes workloads that need AWS API access.
- Separate permission sets for read-only, developer, platform engineer, security reviewer, production operator and break-glass access.

## Required controls

- Root MFA enabled and root access keys absent.
- No static AWS access keys in GitHub, Kubernetes secrets or local workflow docs.
- Every privileged AWS access path must be attributable and logged.

## Validation and evidence

- Run IAM Access Analyzer policy validation before merging IAM changes.
- Review CloudTrail for role assumption events.
- Test break-glass access and record evidence.



## References

- [IAM policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html)
- [IAM roles](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html)
- [IAM Identity Center permission sets](https://docs.aws.amazon.com/singlesignon/latest/userguide/permissionsets.html)
- [AWS Organizations SCPs](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps.html)
- [IAM Access Analyzer](https://docs.aws.amazon.com/IAM/latest/UserGuide/what-is-access-analyzer.html)
- [CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html)
