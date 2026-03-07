# Security Scanning Pipeline Prompt

## Purpose

Design and integrate security scanning into CI/CD pipelines covering SAST, DAST, SCA, container scanning, and secrets detection.

## System Prompt

```
You are a DevSecOps engineer who integrates security scanning into CI/CD pipelines. You balance security thoroughness with developer experience, minimize false positives, and ensure actionable findings. You are familiar with industry-standard scanning tools and compliance frameworks.
```

## Prompt Template

```
Design a security scanning pipeline for this project.

**Technology Stack:** {stack}
**CI/CD Platform:** {platform}
**Container Registry:** {registry}
**Compliance Requirements:** {compliance}

**Current State:**
{current_security}

Design scanning for:

1. **Static Application Security Testing (SAST)**
   - Tool recommendation for {language}
   - Rule configuration and tuning
   - False positive management
   - Integration point in pipeline

2. **Software Composition Analysis (SCA)**
   - Dependency vulnerability scanning
   - License compliance checking
   - Update policy and automation
   - SBOM generation

3. **Container Image Scanning**
   - Base image vulnerability assessment
   - Configuration compliance (CIS benchmark)
   - Layer analysis and optimization
   - Registry scanning policy

4. **Secrets Detection**
   - Pre-commit hooks
   - Pipeline scanning
   - Historical scan for leaked secrets
   - Remediation workflow

5. **Dynamic Application Security Testing (DAST)**
   - When and where to run
   - Scope and target configuration
   - Authentication handling
   - Result triage process

6. **Policy and Governance**
   - Severity thresholds for blocking builds
   - Exception and waiver process
   - Reporting and dashboards
   - SLA for vulnerability remediation

Provide:
- Pipeline configuration with scanning stages
- Tool-specific configuration files
- Threshold and policy definitions
- Developer feedback integration
```

## Tool Recommendations

| Category | Tools | Best For |
|----------|-------|----------|
| SAST | Semgrep, CodeQL, SonarQube | Code pattern analysis |
| SCA | Snyk, Dependabot, Trivy | Dependency vulnerabilities |
| Container | Trivy, Grype, Prisma Cloud | Image scanning |
| Secrets | GitLeaks, TruffleHog, detect-secrets | Credential detection |
| DAST | OWASP ZAP, Nuclei, Burp Suite | Runtime vulnerability testing |

## Severity Policy Template

```yaml
security_policy:
  block_on:
    critical: true
    high: true
    medium: false
    low: false
  sla_days:
    critical: 1
    high: 7
    medium: 30
    low: 90
  exceptions:
    require_approval: true
    max_duration_days: 90
    review_cadence: weekly
```
