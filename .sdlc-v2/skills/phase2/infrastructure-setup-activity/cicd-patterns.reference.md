# CI/CD Patterns Reference

## Overview

Continuous Integration and Continuous Deployment automate the build,
test, and release process for faster, more reliable delivery.

---

## CI Pipeline Stages

### Standard Pipeline

```
┌─────────┐   ┌──────┐   ┌──────────┐   ┌──────────┐   ┌────────┐
│ Checkout│ → │ Build│ → │Unit Tests│ → │Integration│ → │ Deploy │
└─────────┘   └──────┘   └──────────┘   └──────────┘   └────────┘
```

### Detailed Stages

| Stage | Purpose | Duration |
|-------|---------|----------|
| Checkout | Get code | < 30s |
| Install | Dependencies | 1-3 min |
| Lint | Code quality | < 1 min |
| Build | Compile/bundle | 1-5 min |
| Unit Test | Fast tests | 1-3 min |
| Integration | API tests | 2-5 min |
| Security Scan | Vulnerabilities | 1-3 min |
| E2E Test | Full flow | 5-15 min |
| Deploy | Ship it | 2-10 min |

---

## GitHub Actions Example

```yaml
name: CI

on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

jobs:
  build:
    runs-on: ubuntu-latest
    
    steps:
      - uses: actions/checkout@v4
      
      - name: Setup Node
        uses: actions/setup-node@v4
        with:
          node-version: '20'
          cache: 'npm'
      
      - name: Install dependencies
        run: npm ci
      
      - name: Lint
        run: npm run lint
      
      - name: Build
        run: npm run build
      
      - name: Test
        run: npm test -- --coverage
      
      - name: Upload coverage
        uses: codecov/codecov-action@v3

  deploy:
    needs: build
    if: github.ref == 'refs/heads/main'
    runs-on: ubuntu-latest
    
    steps:
      - name: Deploy to staging
        run: |
          # Deployment commands
```

---

## Quality Gates

### PR Quality Gates

| Gate | Requirement | Blocks Merge |
|------|-------------|--------------|
| Build | Must pass | Yes |
| Unit tests | Must pass | Yes |
| Coverage | ≥ 80% | Yes |
| Lint | No errors | Yes |
| Security scan | No critical | Yes |
| Review approval | ≥ 1 | Yes |

### Deployment Gates

| Environment | Gate |
|-------------|------|
| Development | Auto-deploy on merge |
| Staging | Auto-deploy, smoke tests |
| Production | Manual approval + tests |

---

## Deployment Strategies

### Blue-Green Deployment

```
┌──────────────────────────────────┐
│            Load Balancer          │
└─────────────┬────────────────────┘
              │
      ┌───────┴───────┐
      ▼               ▼
┌──────────┐    ┌──────────┐
│   Blue   │    │  Green   │
│ (v1.0)   │    │ (v1.1)   │
│ [active] │    │ [standby]│
└──────────┘    └──────────┘
```

**Process**: Deploy to inactive → Test → Switch traffic

### Canary Deployment

```
Traffic: 100% ──────────────────────────▶
         ├── 95% to v1.0 (stable)
         └── 5% to v1.1 (canary) → gradually increase
```

**Process**: Route small % to new version → Monitor → Increase

### Rolling Deployment

```
Instance 1: v1.0 → v1.1 ✓
Instance 2: v1.0 → v1.1 ✓
Instance 3: v1.0 → v1.1 ✓
Instance 4: v1.0 → v1.1 ✓
```

**Process**: Update one instance at a time

---

## Environment Strategy

| Environment | Purpose | Deploy Trigger |
|-------------|---------|----------------|
| Local | Developer testing | Manual |
| Development | Integration testing | Push to develop |
| Staging | Pre-prod validation | Merge to main |
| Production | Live users | Manual approval |

### Environment Parity

Keep environments as similar as possible:
- Same Docker images
- Same configuration structure
- Same database schema
- Different credentials only

---

## Secrets Management

### Don't Do This

```yaml
# NEVER commit secrets
env:
  API_KEY: "sk-1234567890"  # ❌ BAD
```

### Do This

```yaml
# Use secrets management
env:
  API_KEY: ${{ secrets.API_KEY }}  # ✅ GOOD
```

### Secret Sources

| Platform | Secret Management |
|----------|-------------------|
| GitHub | GitHub Secrets |
| Azure | Key Vault |
| AWS | Secrets Manager |
| GCP | Secret Manager |

---

## Pipeline Optimization

### Caching

```yaml
- uses: actions/cache@v3
  with:
    path: ~/.npm
    key: ${{ runner.os }}-node-${{ hashFiles('**/package-lock.json') }}
```

### Parallelization

```yaml
jobs:
  lint:
    runs-on: ubuntu-latest
    # Runs in parallel with test
  
  test:
    runs-on: ubuntu-latest
    # Runs in parallel with lint
  
  deploy:
    needs: [lint, test]
    # Waits for both
```

### Conditional Steps

```yaml
- name: Deploy
  if: github.ref == 'refs/heads/main'
  run: ./deploy.sh
```

---

## Quick Reference

**Every PR should**:
- Build successfully
- Pass all tests
- Meet coverage threshold
- Pass security scan
- Be reviewed

**Pipeline targets**:
- Total time: < 10 minutes
- Feedback: < 5 minutes for fast tests
- Deploy: < 5 minutes
