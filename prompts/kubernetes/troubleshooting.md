# Kubernetes Troubleshooting Prompt

## Purpose

Systematically diagnose and resolve Kubernetes issues including pod failures, networking problems, storage issues, and performance degradation.

## System Prompt

```
You are a senior Kubernetes administrator and troubleshooter. You diagnose issues systematically, starting with the most common causes and working toward less obvious ones. You provide kubectl commands for diagnosis and specific fixes for each issue.
```

## Prompt Template

```
Help me troubleshoot this Kubernetes issue.

**Cluster Info:**
- Kubernetes version: {version}
- Cloud provider: {provider}
- Cluster type: {type}  (EKS / GKE / AKS / self-managed)

**Problem Description:**
{description}

**Affected Resources:**
- Namespace: {namespace}
- Resource type: {resource_type}  (Pod / Deployment / Service / Ingress / etc.)
- Resource name: {resource_name}

**Symptoms:**
{symptoms}

**kubectl Output:**
```
{kubectl_output}
```

**Events:**
```
{events}
```

**Recent Changes:**
{changes}

Please provide:
1. **Initial Assessment**: What the symptoms suggest
2. **Diagnostic Commands**: kubectl commands to gather more information
3. **Root Cause Analysis**: Most likely causes ranked by probability
4. **Resolution Steps**: Fix for each potential cause
5. **Verification**: How to confirm the issue is resolved
6. **Prevention**: How to avoid this issue in the future
```

## Common Issue Patterns

### Pod Not Starting
```
Pod {name} is stuck in {state} state.

kubectl describe pod output:
{describe_output}

kubectl logs output:
{logs}

Diagnose: CrashLoopBackOff, ImagePullBackOff, Pending, Init container failures.
```

### Service Not Reachable
```
Cannot reach service {service_name} from {source}.

Service definition:
{service_yaml}

Endpoints:
{endpoints}

Diagnose: selector mismatch, port mapping, network policies, DNS resolution.
```

### Node Issues
```
Node {node_name} is showing {condition}.

kubectl describe node output:
{describe_output}

Check: resource pressure, disk pressure, PID pressure, network issues, kubelet status.
```

### Performance Degradation
```
Application {app} is experiencing high latency / resource usage.

Resource metrics:
{metrics}

Diagnose: resource limits, HPA configuration, node capacity, throttling.
```
