# Alert Tuning Prompt

## Purpose

Optimize monitoring alerts to reduce noise, eliminate false positives, and ensure critical issues are caught promptly.

## System Prompt

```
You are a site reliability engineer specializing in observability and alert management. You design alerting strategies that minimize alert fatigue while ensuring no critical issue goes undetected. You follow best practices from Google SRE and understand symptom-based vs cause-based alerting.
```

## Prompt Template

```
Review and optimize these monitoring alerts.

**Monitoring Platform:** {platform}  (Prometheus / Datadog / CloudWatch / Grafana)
**Service:** {service}
**SLA/SLO:** {slo}
**On-Call Team Size:** {team_size}

**Current Alerts:**
{alerts}

**Alert Statistics (last 30 days):**
- Total alerts fired: {total}
- Actionable alerts: {actionable}
- False positives: {false_positives}
- Missed incidents: {missed}
- Average response time: {response_time}
- Alert fatigue score: {fatigue}

Optimize across:

1. **Alert Relevance**
   - Remove or merge redundant alerts
   - Convert non-actionable alerts to dashboards
   - Ensure each alert has a clear action

2. **Threshold Tuning**
   - Adjust thresholds based on historical data
   - Implement dynamic thresholds where appropriate
   - Use percentile-based alerting (p99 vs average)

3. **Alert Structure**
   - Proper severity classification (page / ticket / log)
   - Clear alert names and descriptions
   - Runbook links for every paging alert
   - Appropriate grouping and deduplication

4. **SLO-Based Alerting**
   - Define error budget alerts
   - Implement burn rate alerting
   - Multi-window alert strategy

5. **Routing and Escalation**
   - On-call routing rules
   - Escalation policies
   - Business hours vs off-hours routing

Provide optimized alert definitions with rationale for each change.
```

## Alert Quality Checklist

- [ ] Every alert is actionable (someone needs to do something)
- [ ] Alert has a clear severity level
- [ ] Alert includes runbook link
- [ ] Thresholds account for normal variance
- [ ] Alert has appropriate evaluation window
- [ ] Grouping prevents alert storms
- [ ] Resolution is automatically detected

## SLO Burn Rate Template

```
# Multi-window burn rate alerting
# Page if burning through error budget too fast

# Fast burn (2% of budget in 1 hour)
- alert: HighErrorBudgetBurn_Fast
  for: 2m
  expr: |
    error_ratio > (14.4 * error_budget_ratio)
    AND
    error_ratio_1h > (14.4 * error_budget_ratio)

# Slow burn (5% of budget in 6 hours)
- alert: HighErrorBudgetBurn_Slow
  for: 15m
  expr: |
    error_ratio > (6 * error_budget_ratio)
    AND
    error_ratio_6h > (6 * error_budget_ratio)
```
