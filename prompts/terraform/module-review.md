# Terraform Module Review Prompt

## Purpose

Review Terraform modules for best practices, security, maintainability, and operational readiness.

## System Prompt

```
You are a senior infrastructure engineer specializing in Terraform. You review modules against HashiCorp best practices, security benchmarks, and production-readiness criteria. You provide specific, actionable feedback with code examples.
```

## Prompt Template

```
Review this Terraform module for production readiness.

**Module Purpose:** {purpose}
**Target Provider:** {provider}  (AWS / GCP / Azure)
**Terraform Version:** {version}
**Compliance Requirements:** {compliance}

**Module Code:**
```hcl
{code}
```

Evaluate against:

1. **Structure & Organization**
   - File organization (main.tf, variables.tf, outputs.tf, versions.tf)
   - Module composition and reusability
   - Proper use of locals vs variables

2. **Security**
   - Least privilege IAM policies
   - Encryption at rest and in transit
   - No hardcoded secrets or credentials
   - Security group / firewall rule review

3. **Variables & Outputs**
   - Proper type constraints and validation rules
   - Sensible defaults
   - Descriptive descriptions
   - All necessary outputs exposed

4. **State & Lifecycle**
   - Proper use of lifecycle blocks (prevent_destroy, ignore_changes)
   - State management considerations
   - Import-friendly resource definitions

5. **Operational Readiness**
   - Tagging strategy
   - Monitoring and alerting resources
   - Backup and recovery provisions
   - Cost optimization opportunities

For each finding, provide:
- Severity: CRITICAL / HIGH / MEDIUM / LOW
- Current code snippet
- Recommended fix with code
```

## Checklist

- [ ] All resources have consistent tagging
- [ ] Variables have type constraints and descriptions
- [ ] Sensitive variables marked as `sensitive = true`
- [ ] Provider version constraints specified
- [ ] No hardcoded values that should be variables
- [ ] Outputs documented and properly typed
- [ ] README with usage examples exists
