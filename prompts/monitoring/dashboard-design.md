# Dashboard Design Prompt

## Purpose

Design effective monitoring dashboards that provide clear visibility into system health, performance, and business metrics.

## System Prompt

```
You are an observability expert who designs dashboards following the USE method (Utilization, Saturation, Errors) and RED method (Rate, Errors, Duration). You create dashboards that tell a story and enable quick diagnosis during incidents.
```

## Prompt Template

```
Design a monitoring dashboard for this system.

**Dashboard Type:** {type}
  (service overview / infrastructure / SLO / business metrics / incident)
**Monitoring Platform:** {platform}  (Grafana / Datadog / CloudWatch / New Relic)
**Service Architecture:** {architecture}
**Data Sources:** {data_sources}

**Target Audience:** {audience}  (SRE / developers / management / all)
**Key SLOs/KPIs:** {kpis}

Design a dashboard with:

1. **Layout Structure**
   - Information hierarchy (most important metrics at top)
   - Logical grouping of related panels
   - Consistent time range and refresh interval
   - Row organization and panel sizing

2. **Key Panels**
   - Traffic: request rate, active users, throughput
   - Errors: error rate, error breakdown by type, HTTP status codes
   - Latency: p50, p95, p99 response times
   - Saturation: CPU, memory, disk, connection pools

3. **Visual Design**
   - Chart type selection (time series, gauge, stat, heatmap, table)
   - Color coding for severity (green/yellow/red thresholds)
   - Annotations for deployments and incidents
   - Template variables for filtering

4. **Drill-Down Capability**
   - Links to detailed dashboards
   - Variable-based filtering (service, environment, region)
   - Time range zoom for incident investigation

5. **SLO Tracking**
   - Error budget remaining
   - SLO compliance over time windows (7d, 30d)
   - Burn rate visualization

Provide the dashboard specification with panel definitions, queries, and layout.
```

## Dashboard Patterns

### The Four Golden Signals
```
Design panels for:
1. Latency - histogram of request durations
2. Traffic - requests per second
3. Errors - error rate percentage
4. Saturation - resource utilization gauges
```

### USE Method (Infrastructure)
```
For each resource (CPU, memory, disk, network):
- Utilization: percentage of resource capacity used
- Saturation: queue depth, wait time
- Errors: hardware/software error counts
```

### RED Method (Services)
```
For each service endpoint:
- Rate: requests per second
- Errors: failed requests per second
- Duration: response time distribution
```

## Panel Best Practices

| Metric Type | Recommended Chart | Why |
|-------------|-------------------|-----|
| Rate/throughput | Time series line | Shows trends over time |
| Current value | Stat/gauge | Instant status check |
| Distribution | Heatmap/histogram | Shows percentiles and outliers |
| Comparison | Bar chart | Side-by-side comparison |
| Status | Status map | Multi-service health at a glance |
| Breakdown | Pie/table | Categorical distribution |
