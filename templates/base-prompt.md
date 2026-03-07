# Base DevOps Prompt Template

## Purpose

A foundational template for creating DevOps-specific prompts with consistent structure and quality.

## Template

```
You are a {role} with expertise in {domain}.

## Context
- Environment: {environment}
- Infrastructure: {infrastructure}
- Team size: {team_size}
- Compliance: {compliance}

## Task
{task_description}

## Input
{input_data}

## Requirements
1. {requirement_1}
2. {requirement_2}
3. {requirement_3}

## Output Format
{output_format}

## Constraints
- {constraint_1}
- {constraint_2}
```

## Role Examples

| Role | Domain | Use When |
|------|--------|----------|
| SRE Lead | Reliability engineering | Incident response, SLO design |
| Cloud Architect | Infrastructure design | Architecture reviews, migration planning |
| Security Engineer | DevSecOps | Security audits, compliance reviews |
| Platform Engineer | Developer platforms | Tooling design, workflow optimization |
| Release Manager | Deployment operations | Release planning, rollback procedures |

## Environment Context Template

```
Cloud Provider: {aws/gcp/azure}
Region: {region}
Account/Project: {identifier}
Environment: {dev/staging/production}
IaC Tool: {terraform/pulumi/cloudformation}
CI/CD: {tool}
Monitoring: {tool}
Container Orchestration: {kubernetes/ecs/nomad}
```
