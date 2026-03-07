# CI/CD Pipeline Design Prompt

## Purpose

Design robust CI/CD pipelines with proper stages, quality gates, security scanning, and deployment strategies.

## System Prompt

```
You are a CI/CD architect who designs pipelines for reliability, speed, and security. You follow trunk-based development practices, implement proper quality gates, and design for both speed and safety. You are familiar with GitHub Actions, GitLab CI, Jenkins, and CircleCI.
```

## Prompt Template

```
Design a CI/CD pipeline for this project.

**Project Type:** {type}  (web app / microservice / library / infrastructure)
**Language/Framework:** {stack}
**Repository Platform:** {platform}  (GitHub / GitLab / Bitbucket)
**CI/CD Tool:** {tool}  (GitHub Actions / GitLab CI / Jenkins / CircleCI)
**Deployment Target:** {target}  (Kubernetes / ECS / Lambda / VM / CDN)
**Environments:** {environments}  (dev / staging / production)

**Requirements:**
- Build time target: {build_time}
- Deployment frequency: {frequency}
- Rollback capability: {rollback}
- Compliance: {compliance}

Design a pipeline with:

1. **Build Stage**
   - Dependency caching strategy
   - Parallel build steps
   - Artifact management

2. **Test Stage**
   - Unit tests with coverage thresholds
   - Integration tests
   - End-to-end tests (when applicable)
   - Test parallelization

3. **Security Stage**
   - SAST (static analysis)
   - Dependency vulnerability scanning
   - Container image scanning
   - Secrets detection

4. **Quality Gates**
   - Coverage thresholds
   - Linting and formatting
   - Breaking change detection
   - Performance regression checks

5. **Deployment Stage**
   - Deployment strategy (blue-green / canary / rolling)
   - Environment promotion flow
   - Smoke tests post-deploy
   - Automatic rollback triggers

6. **Notifications**
   - Build status notifications
   - Deployment notifications
   - Failure alerts

Provide the pipeline configuration file with comments.
```

## Pipeline Templates

### GitHub Actions - Microservice
```
Design a GitHub Actions pipeline for a {language} microservice deployed to Kubernetes.
Include: build, test, scan, deploy to staging, approval gate, deploy to production.
```

### GitLab CI - Monorepo
```
Design a GitLab CI pipeline for a monorepo with {n} services.
Include: change detection, parallel service builds, shared test infrastructure.
```

### Jenkins - Enterprise
```
Design a Jenkins pipeline for an enterprise Java application.
Include: Sonar quality gate, Nexus artifact storage, approval workflow, audit trail.
```
