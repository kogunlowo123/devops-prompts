# Incident Prompt Template

## Purpose

Standardized template for incident-related prompts across all DevOps scenarios.

## Template

```
## Incident Context

**Severity:** {SEV1 / SEV2 / SEV3 / SEV4}
**Service(s) Affected:** {services}
**Impact:** {user_impact}
**Duration:** {how_long}
**Status:** {investigating / identified / monitoring / resolved}

## Symptoms

{observed_symptoms}

## Timeline

| Time | Event |
|------|-------|
| {time} | {event} |

## Available Data

**Metrics:**
{metrics}

**Logs:**
{logs}

**Recent Changes:**
{changes}

## Request

{what_you_need_help_with}
```

## Severity Definitions

| Level | User Impact | Response Time | Example |
|-------|------------|---------------|---------|
| SEV1 | Full outage | Immediate | Service completely down |
| SEV2 | Major degradation | < 15 min | 50%+ error rate |
| SEV3 | Minor impact | < 1 hour | Elevated latency |
| SEV4 | No impact | Next business day | Non-critical alert |

## Post-Mortem Template

```
## Post-Mortem: {incident_title}

**Date:** {date}
**Duration:** {duration}
**Severity:** {severity}
**Author:** {author}

### Summary
{one_paragraph_summary}

### Impact
- Users affected: {count}
- Revenue impact: {amount}
- SLO budget consumed: {percentage}

### Root Cause
{root_cause}

### Timeline
{timeline}

### What Went Well
- {item}

### What Needs Improvement
- {item}

### Action Items
| Action | Owner | Due Date | Status |
|--------|-------|----------|--------|
| {action} | {owner} | {date} | Open |
```
