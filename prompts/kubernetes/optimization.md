# Kubernetes Optimization Prompt

## Purpose

Optimize Kubernetes workloads for cost efficiency, performance, reliability, and resource utilization.

## System Prompt

```
You are a Kubernetes optimization specialist focused on cost reduction, performance tuning, and operational efficiency. You balance resource requests and limits, right-size workloads, and implement best practices for production clusters.
```

## Prompt Template

```
Optimize this Kubernetes configuration for production readiness.

**Optimization Goals:** {goals}
  (cost reduction / performance / reliability / all)

**Current Configuration:**
```yaml
{configuration}
```

**Current Metrics:**
- CPU utilization: {cpu_util}
- Memory utilization: {mem_util}
- Pod count: {pod_count}
- Monthly cost: {cost}

**Constraints:**
- SLA requirement: {sla}
- Peak traffic pattern: {traffic_pattern}
- Budget limit: {budget}

Optimize across these dimensions:

1. **Resource Requests & Limits**
   - Right-size based on actual usage
   - Set appropriate QoS classes
   - Configure LimitRanges and ResourceQuotas

2. **Autoscaling**
   - HPA configuration (metrics, thresholds, behavior)
   - VPA recommendations
   - Cluster autoscaler tuning

3. **Pod Scheduling**
   - Node affinity and anti-affinity rules
   - Topology spread constraints
   - Priority classes and preemption

4. **Cost Optimization**
   - Spot/preemptible instance usage
   - Namespace resource quotas
   - Idle resource identification

5. **Reliability**
   - Pod Disruption Budgets
   - Health check tuning (liveness, readiness, startup probes)
   - Graceful shutdown configuration

Provide the optimized YAML with comments explaining each change.
```

## Quick Optimization Checks

### Resource Right-Sizing
```
Review these resource requests and limits against actual usage:

Current requests/limits:
{resource_config}

Actual usage (p50/p95/p99):
{usage_data}

Recommend new values with justification.
```

### HPA Tuning
```
Optimize this HPA configuration:
{hpa_yaml}

Traffic pattern: {pattern}
Current scaling behavior: {behavior}

Issues: {issues}  (too aggressive / too slow / oscillating)
```

### Probe Optimization
```
Review and optimize health check configuration:
{probe_config}

Application startup time: {startup_time}
Known failure modes: {failure_modes}

Optimize timing to minimize false positives while detecting real failures quickly.
```
