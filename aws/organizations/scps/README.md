# bfstore AWS Service Control Policies

Draft SCP policy pack for the bfstore AWS Organisation.

## Important safety notes

- Keep the AWS-managed `FullAWSAccess` SCP attached unless you are deliberately moving to an allow-list SCP model.
- Test every SCP in Sandbox first before attaching to shared, stage, prod, security, log archive or network accounts.
- Replace placeholder role names, bucket names and account-specific naming patterns before production use.
- SCPs do not grant access. They only define the maximum permissions available to identities in member accounts.
- SCPs do not apply to the management account.
- Some policies contain break-glass or IaC role exceptions. Create and test those roles before relying on the SCPs.

## Recommended attachment order

1. `deny-leave-organization.json`
2. `restrict-member-root-user.json`
3. `deny-iam-users-and-access-keys.json`
4. `deny-unsupported-regions.json`
5. `protect-security-and-audit-services.json`
6. `protect-log-archive.json`
7. `protect-network-control-plane.json`
8. `protect-prod-critical-resources.json`
9. `deny-dangerous-iam-mutation.json`
10. `sandbox-cost-and-region-guardrails.json`

## Suggested locations

```text
bfstore-platform-infra/
└── aws/
    └── organizations/
        └── scps/
            ├── README.md
            └── policies/
```

