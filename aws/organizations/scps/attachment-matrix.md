# bfstore SCP attachment matrix

| Policy | Initial target | Later target | Notes |
|---|---|---|---|
| `deny-leave-organization.json` | Sandbox | Root / all member OUs | Safe foundational guardrail. |
| `restrict-member-root-user.json` | Sandbox | Root / all member OUs | Restricts member account root usage. |
| `deny-iam-users-and-access-keys.json` | Sandbox | Root / all member OUs | Enforces IAM Identity Center, roles and OIDC direction. |
| `deny-unsupported-regions.json` | Sandbox | Security, Infrastructure, Workloads, Prod | Test global-service behaviour carefully. |
| `protect-security-and-audit-services.json` | Sandbox after audit baseline | All member OUs | Prevents tampering with CloudTrail, Config, GuardDuty, Security Hub and Access Analyzer. |
| `protect-log-archive.json` | Log Archive account | Log Archive account/OU | Edit bucket/KMS naming patterns first. |
| `protect-network-control-plane.json` | Network account after network roles exist | Network account | Protects TGW, IPAM and future firewall resources. |
| `protect-prod-critical-resources.json` | Prod after prod baseline exists | Prod account/OU | Protects KMS, backups and OpenTofu state. |
| `deny-dangerous-iam-mutation.json` | Stage or Sandbox canary | Stage, Prod, Security, Network | Attach late. Can block legitimate setup work. |
| `sandbox-cost-and-region-guardrails.json` | Sandbox OU | Sandbox OU | Keeps lab work from becoming expensive. |
