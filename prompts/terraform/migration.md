# Terraform Migration Prompt

## Purpose

Plan and execute Terraform migrations including version upgrades, provider changes, state restructuring, and resource refactoring.

## System Prompt

```
You are a Terraform migration specialist. You plan migrations with zero downtime, create detailed runbooks, and account for state management complexities. You always provide rollback procedures and validation steps.
```

## Prompt Template

```
Plan a Terraform migration for the following scenario.

**Migration Type:** {type}
  (version upgrade / provider migration / state refactor / module extraction / monolith split)

**Current State:**
- Terraform version: {current_version}
- Provider versions: {current_providers}
- State backend: {state_backend}
- Resource count: {resource_count}

**Target State:**
- Terraform version: {target_version}
- Provider versions: {target_providers}
- State backend: {target_backend}

**Current Code:**
```hcl
{current_code}
```

**Constraints:**
- Downtime tolerance: {downtime_tolerance}
- Team size: {team_size}
- Timeline: {timeline}

Please provide:
1. **Risk Assessment**: What could go wrong and impact analysis
2. **Prerequisites**: What must be in place before starting
3. **Migration Plan**: Step-by-step procedure with commands
4. **State Operations**: Required state mv, import, or rm commands
5. **Code Changes**: Required HCL modifications
6. **Validation**: How to verify each step succeeded
7. **Rollback Plan**: How to reverse the migration at each stage
8. **Communication Plan**: Who to notify and when
```

## Common Migrations

### Version 0.x to 1.x
```
Plan migration from Terraform {old_version} to {new_version}.
Highlight: deprecated syntax, removed features, required code changes.
Include: upgrade path, compatibility issues, provider updates needed.
```

### State Backend Migration
```
Migrate Terraform state from {source_backend} to {target_backend}.
Include: state locking considerations, team coordination, DNS/endpoint changes.
Provide exact commands for backup, migration, and verification.
```

### Module Extraction
```
Extract these resources from a monolithic Terraform configuration into a reusable module:
Resources: {resource_list}

Current code: {code}

Provide: module interface (variables/outputs), state move commands,
updated root module calling the new module.
```

## Safety Checklist

- [ ] State backup taken and verified
- [ ] Plan output reviewed (no unexpected destroys)
- [ ] Team notified of migration window
- [ ] Rollback procedure documented and tested
- [ ] CI/CD pipelines paused during migration
- [ ] Post-migration validation queries prepared
