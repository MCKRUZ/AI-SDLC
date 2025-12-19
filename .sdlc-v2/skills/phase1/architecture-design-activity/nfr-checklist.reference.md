# Non-Functional Requirements (NFR) Checklist

## Overview

NFRs define system qualities that determine HOW the system performs,
not WHAT it does. Every NFR should be measurable with specific targets.

---

## Performance Requirements

### Response Time

| Metric | Target | Measurement |
|--------|--------|-------------|
| API response (p50) | < 200ms | Median response time |
| API response (p95) | < 500ms | 95th percentile |
| API response (p99) | < 1000ms | 99th percentile |
| Page load (initial) | < 3s | Time to first contentful paint |
| Page load (interactive) | < 5s | Time to interactive |
| Database query | < 100ms | Average query execution |

**How to Specify:**
```markdown
NFR-PERF-001: API Response Time
- p50 response time shall be < 200ms
- p95 response time shall be < 500ms
- Measured under normal load (1000 concurrent users)
- Excludes network latency from client
```

### Throughput

| Metric | Target | Measurement |
|--------|--------|-------------|
| Requests per second | X RPS | Sustained load |
| Transactions per second | X TPS | Business transactions |
| Messages per second | X MPS | Queue processing |
| Concurrent users | X users | Simultaneous active sessions |

**How to Specify:**
```markdown
NFR-PERF-002: System Throughput
- System shall handle 10,000 requests per second
- With 5,000 concurrent users
- While maintaining response time targets
- Measured during peak load testing
```

### Resource Utilization

| Metric | Target | Measurement |
|--------|--------|-------------|
| CPU utilization | < 70% | Under normal load |
| Memory utilization | < 80% | Under normal load |
| Disk I/O | < 60% | Under normal load |
| Network bandwidth | < 50% | Under normal load |

---

## Scalability Requirements

### Horizontal Scaling

```markdown
NFR-SCALE-001: Horizontal Scalability
- System shall scale from 2 to 20 instances
- Auto-scaling triggered at 70% CPU
- Scale-out time < 5 minutes
- No session affinity required
```

### Vertical Scaling

```markdown
NFR-SCALE-002: Vertical Scalability
- Database shall support vertical scaling
- From 4 vCPU/16GB to 32 vCPU/128GB
- Without downtime (for reads)
- < 5 minute write downtime
```

### Data Scaling

```markdown
NFR-SCALE-003: Data Volume Scaling
- System shall handle 100M records
- With < 10% performance degradation
- Query performance maintained with proper indexing
- Archive strategy for data > 2 years old
```

---

## Availability Requirements

### Uptime

| Level | Uptime | Downtime/Year | Downtime/Month |
|-------|--------|---------------|----------------|
| 99% | Two 9s | 3.65 days | 7.3 hours |
| 99.9% | Three 9s | 8.76 hours | 43.8 minutes |
| 99.95% | Three and half 9s | 4.38 hours | 21.9 minutes |
| 99.99% | Four 9s | 52.6 minutes | 4.38 minutes |

**How to Specify:**
```markdown
NFR-AVAIL-001: System Availability
- System shall maintain 99.9% availability
- Measured monthly (rolling 30 days)
- Excluding scheduled maintenance windows
- Scheduled maintenance < 4 hours/month
```

### Fault Tolerance

```markdown
NFR-AVAIL-002: Fault Tolerance
- System shall survive single component failure
- No single point of failure in production
- Automatic failover within 30 seconds
- Data loss < 1 second (RPO)
```

### Disaster Recovery

```markdown
NFR-AVAIL-003: Disaster Recovery
- RTO (Recovery Time Objective): < 4 hours
- RPO (Recovery Point Objective): < 1 hour
- Geographic redundancy: multi-region
- Tested quarterly
```

---

## Security Requirements

### Authentication

```markdown
NFR-SEC-001: Authentication
- Multi-factor authentication for admin users
- Password complexity: 12+ chars, mixed case, numbers, symbols
- Account lockout after 5 failed attempts
- Session timeout: 30 minutes inactive
- Secure password reset via email verification
```

### Authorization

```markdown
NFR-SEC-002: Authorization
- Role-based access control (RBAC)
- Principle of least privilege
- Authorization checked on every request
- Audit log of permission changes
```

### Data Protection

```markdown
NFR-SEC-003: Data Protection
- Encryption at rest: AES-256
- Encryption in transit: TLS 1.3
- PII data encrypted with separate keys
- Key rotation: every 90 days
- Secure key storage (HSM or cloud KMS)
```

### Compliance

```markdown
NFR-SEC-004: Compliance
- GDPR compliant (data residency, right to forget)
- SOC 2 Type II controls
- PCI-DSS compliant (if processing payments)
- Annual security audit
- Penetration testing quarterly
```

---

## Reliability Requirements

### Error Rates

```markdown
NFR-REL-001: Error Rates
- Error rate < 0.1% of all requests
- No unhandled exceptions in production
- Circuit breaker triggers at 50% error rate
- Graceful degradation for non-critical features
```

### Data Integrity

```markdown
NFR-REL-002: Data Integrity
- ACID transactions for financial data
- Referential integrity enforced
- Checksums for file uploads
- Audit trail for data changes
```

### Recoverability

```markdown
NFR-REL-003: Recoverability
- Automated backups every 6 hours
- Point-in-time recovery capability
- Backup retention: 30 days
- Restore tested monthly
- Restore time < 2 hours
```

---

## Maintainability Requirements

### Code Quality

```markdown
NFR-MAINT-001: Code Quality
- Code coverage > 80%
- Cyclomatic complexity < 10
- No critical/high security vulnerabilities
- Technical debt ratio < 5%
- All code peer-reviewed
```

### Documentation

```markdown
NFR-MAINT-002: Documentation
- API documented with OpenAPI 3.0
- Architecture diagrams (C4 model)
- Runbooks for common operations
- README for each service
- Changelog maintained
```

### Observability

```markdown
NFR-MAINT-003: Observability
- Structured logging (JSON format)
- Distributed tracing (correlation IDs)
- Metrics dashboards (Grafana/similar)
- Alerting for critical metrics
- Log retention: 30 days
```

### Deployability

```markdown
NFR-MAINT-004: Deployability
- Zero-downtime deployments
- Automated rollback capability
- Blue-green or canary deployment support
- Deployment time < 15 minutes
- Feature flags for gradual rollout
```

---

## Usability Requirements

### Accessibility

```markdown
NFR-USE-001: Accessibility
- WCAG 2.1 Level AA compliance
- Screen reader compatible
- Keyboard navigation support
- Color contrast ratio > 4.5:1
- Alt text for all images
```

### Internationalization

```markdown
NFR-USE-002: Internationalization
- Support for UTF-8 encoding
- Date/time localization
- Currency formatting by locale
- RTL language support (if needed)
- Translation framework integrated
```

### Browser/Device Support

```markdown
NFR-USE-003: Browser Support
- Chrome (last 2 versions)
- Firefox (last 2 versions)
- Safari (last 2 versions)
- Edge (last 2 versions)
- Mobile: iOS 14+, Android 10+
```

---

## Compatibility Requirements

### Integration

```markdown
NFR-COMPAT-001: Integration
- REST API follows OpenAPI 3.0 spec
- API versioning via URL path (/v1/, /v2/)
- Backward compatibility for 2 major versions
- Deprecation notice: 6 months minimum
```

### Data Formats

```markdown
NFR-COMPAT-002: Data Formats
- JSON for API responses
- CSV/Excel export capability
- PDF generation for reports
- Standard date format: ISO 8601
```

---

## NFR Template

```markdown
## NFR-[CATEGORY]-[NUMBER]: [Title]

**Category**: [Performance | Scalability | Availability | Security | ...]
**Priority**: [Critical | High | Medium | Low]
**Source**: [Stakeholder, compliance requirement, business need]

### Requirement

[Clear statement of the requirement]

### Measurement

- **Metric**: [What to measure]
- **Target**: [Specific value]
- **Method**: [How to measure]
- **Frequency**: [How often to measure]

### Validation

- [ ] Test case defined
- [ ] Monitoring in place
- [ ] Alerting configured

### Notes

[Any additional context or constraints]
```

---

## Quick Reference Checklist

### Essential NFRs (Must Define)

- [ ] Response time targets (p50, p95, p99)
- [ ] Availability target (99.X%)
- [ ] Authentication method
- [ ] Data encryption (at rest, in transit)
- [ ] Backup frequency and retention
- [ ] Error rate target

### Important NFRs (Should Define)

- [ ] Scalability limits
- [ ] Browser/device support
- [ ] Accessibility standard
- [ ] Logging and monitoring
- [ ] Deployment strategy
- [ ] RTO/RPO targets

### Nice to Have NFRs

- [ ] Performance under stress
- [ ] Internationalization scope
- [ ] Code quality metrics
- [ ] Technical debt limits
