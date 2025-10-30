# Environment Configuration

**Project Name**: [Project name from constitution]  
**Date Created**: [YYYY-MM-DD]  
**Last Updated**: [YYYY-MM-DD]  
**Version**: [v1.0, v2.0, etc.]  
**Created By**: [DevOps Scaffolder / Infrastructure Lead]  
**Technology Stack**: [Backend + Frontend + Infrastructure]

---

## Purpose of This Document

This Environment Configuration document defines **all environment-specific settings, configurations, and infrastructure** required to run the application across different environments (development, staging, production). It serves as the authoritative reference for environment setup and deployment.

**What This Document Contains**:
- Environment variable specifications
- Docker container configurations
- CI/CD pipeline settings
- Infrastructure requirements
- Security configurations
- Monitoring and logging setup
- Environment-specific differences

**What This Document Does NOT Contain**:
- Application source code (see src/)
- Repository structure (see repository-structure.md)
- Development workflow (see docs/development/)
- Business logic or requirements (see spec.md)

**Who Uses This Document**:
- DevOps Engineers: Configure and deploy environments
- Developers: Understand environment requirements
- Operations Team: Monitor and maintain systems
- Security Team: Validate security configurations
- New Team Members: Set up local development

**Traceability**:
- **From**: architecture.md (infrastructure design), constitution.md (NFRs)
- **To**: Actual environment configurations (Docker, K8s, cloud)
- **Related**: repository-structure.md, repository-setup.prompt.md

---

## Environment Overview

**Environments Defined**:
1. **Development** (Local) - Individual developer machines
2. **Staging** - Pre-production testing environment
3. **Production** - Live production environment

**Environment Strategy**: [Description of environment strategy]

---

## Development Environment (Local)

### Purpose

Individual developer machines for feature development and testing.

### Infrastructure

**Runtime**:
- Docker Desktop 24.0+
- Docker Compose 2.20+

**Services**:
- Backend API (containerized or local)
- Frontend (containerized or local)
- PostgreSQL database (containerized)
- Redis cache (containerized, optional)
- pgAdmin (containerized, optional)

### Configuration

#### Docker Compose (`docker-compose.yml`)

```yaml
version: '3.8'

services:
  database:
    image: postgres:16-alpine
    container_name: ${PROJECT_NAME:-app}-db-dev
    environment:
      POSTGRES_DB: ${DATABASE_NAME:-appdb}
      POSTGRES_USER: ${DATABASE_USER:-postgres}
      POSTGRES_PASSWORD: ${DATABASE_PASSWORD:-postgres}
    ports:
      - "5432:5432"
    volumes:
      - postgres-data-dev:/var/lib/postgresql/data
      - ./scripts/init-db.sql:/docker-entrypoint-initdb.d/init.sql
    healthcheck:
      test: ["CMD-SHELL", "pg_isready -U ${DATABASE_USER:-postgres}"]
      interval: 10s
      timeout: 5s
      retries: 5
    networks:
      - app-network-dev

  cache:
    image: redis:7.2-alpine
    container_name: ${PROJECT_NAME:-app}-cache-dev
    ports:
      - "6379:6379"
    volumes:
      - redis-data-dev:/data
    healthcheck:
      test: ["CMD", "redis-cli", "ping"]
      interval: 10s
      timeout: 3s
      retries: 5
    networks:
      - app-network-dev

  backend:
    build:
      context: .
      dockerfile: infrastructure/docker/backend.Dockerfile
      target: development
    container_name: ${PROJECT_NAME:-app}-api-dev
    environment:
      ASPNETCORE_ENVIRONMENT: Development
      ASPNETCORE_URLS: http://+:5000
      ConnectionStrings__DefaultConnection: "Host=database;Port=5432;Database=${DATABASE_NAME:-appdb};Username=${DATABASE_USER:-postgres};Password=${DATABASE_PASSWORD:-postgres}"
      Redis__Host: cache
      Redis__Port: 6379
      Logging__LogLevel__Default: Debug
      Logging__LogLevel__Microsoft: Information
    ports:
      - "5000:5000"
    depends_on:
      database:
        condition: service_healthy
      cache:
        condition: service_healthy
    volumes:
      - ./src/backend:/src/backend:cached
      - backend-nuget-dev:/root/.nuget/packages
    networks:
      - app-network-dev
    restart: unless-stopped

  frontend:
    build:
      context: .
      dockerfile: infrastructure/docker/frontend.Dockerfile
      target: development
    container_name: ${PROJECT_NAME:-app}-frontend-dev
    environment:
      NODE_ENV: development
      VITE_API_URL: http://localhost:5000/api
      VITE_APP_NAME: ${PROJECT_NAME:-App}
    ports:
      - "3000:3000"
    depends_on:
      - backend
    volumes:
      - ./src/frontend:/app:cached
      - frontend-nodemodules-dev:/app/node_modules
    networks:
      - app-network-dev
    restart: unless-stopped

  pgadmin:
    image: dpage/pgadmin4:latest
    container_name: ${PROJECT_NAME:-app}-pgadmin-dev
    environment:
      PGADMIN_DEFAULT_EMAIL: admin@example.com
      PGADMIN_DEFAULT_PASSWORD: admin
      PGADMIN_CONFIG_SERVER_MODE: 'False'
    ports:
      - "5050:80"
    volumes:
      - pgadmin-data-dev:/var/lib/pgadmin
    depends_on:
      - database
    networks:
      - app-network-dev
    profiles:
      - tools

volumes:
  postgres-data-dev:
    driver: local
  redis-data-dev:
    driver: local
  pgadmin-data-dev:
    driver: local
  backend-nuget-dev:
    driver: local
  frontend-nodemodules-dev:
    driver: local

networks:
  app-network-dev:
    driver: bridge
```

#### Environment Variables (`.env`)

**Location**: Project root (gitignored)  
**Template**: `.env.example` (committed)

```bash
# Project
PROJECT_NAME=myproject

# Database
DATABASE_HOST=localhost
DATABASE_PORT=5432
DATABASE_NAME=myproject_dev
DATABASE_USER=postgres
DATABASE_PASSWORD=devpassword123

# Application
ASPNETCORE_ENVIRONMENT=Development
API_BASE_URL=http://localhost:5000
FRONTEND_URL=http://localhost:3000

# JWT Authentication
JWT_SECRET_KEY=dev-secret-key-min-32-characters-change-in-prod
JWT_ISSUER=http://localhost:5000
JWT_AUDIENCE=http://localhost:3000
JWT_EXPIRATION_HOURS=24

# Redis
REDIS_HOST=localhost
REDIS_PORT=6379

# External Services (Development)
SMTP_HOST=localhost
SMTP_PORT=1025
SMTP_USER=
SMTP_PASSWORD=
SMTP_FROM=noreply@localhost

# Logging
LOG_LEVEL=Debug
LOG_TO_CONSOLE=true
LOG_TO_FILE=false

# Feature Flags
FEATURE_USER_REGISTRATION=true
FEATURE_SOCIAL_LOGIN=false
FEATURE_ANALYTICS=false
```

### Access URLs

| Service | URL | Credentials |
|---------|-----|-------------|
| Frontend | http://localhost:3000 | - |
| Backend API | http://localhost:5000 | - |
| Swagger UI | http://localhost:5000/swagger | - |
| pgAdmin | http://localhost:5050 | admin@example.com / admin |
| PostgreSQL | localhost:5432 | postgres / devpassword123 |
| Redis | localhost:6379 | No auth |

### Resource Limits

```yaml
# Development - No strict limits, optimize for convenience
services:
  backend:
    deploy:
      resources:
        limits:
          cpus: '2'
          memory: 2G
  
  frontend:
    deploy:
      resources:
        limits:
          cpus: '1'
          memory: 1G
  
  database:
    deploy:
      resources:
        limits:
          cpus: '1'
          memory: 1G
```

### Security Configuration

**Development Security (Relaxed)**:
- HTTPS: Optional (HTTP allowed)
- CORS: Permissive (allow localhost origins)
- Authentication: JWT with long expiration (24 hours)
- Rate Limiting: Disabled
- SQL Injection Protection: Enabled (always)
- XSS Protection: Enabled (always)

---

## Staging Environment

### Purpose

Pre-production environment for QA testing, UAT, and release validation.

### Infrastructure

**Hosting**: [Azure App Service / AWS ECS / Kubernetes cluster]  
**Region**: [e.g., East US, eu-west-1]  
**Scaling**: Fixed (2 instances) or Auto-scaling (2-4 instances)

**Services**:
- Backend API (containerized, 2+ replicas)
- Frontend (containerized, 2+ replicas)
- PostgreSQL (managed service: Azure Database / RDS)
- Redis (managed service: Azure Cache / ElastiCache)
- Load Balancer (cloud provider managed)

### Configuration

#### Environment Variables

```bash
# Project
PROJECT_NAME=myproject
ENVIRONMENT=Staging

# Database (Managed Service)
DATABASE_HOST=myproject-staging.postgres.database.azure.com
DATABASE_PORT=5432
DATABASE_NAME=myproject_staging
DATABASE_USER=dbadmin@myproject-staging
DATABASE_PASSWORD=${SECRET:DATABASE_PASSWORD}  # From Key Vault/Secrets Manager
DATABASE_SSL_MODE=require

# Application
ASPNETCORE_ENVIRONMENT=Staging
API_BASE_URL=https://api-staging.example.com
FRONTEND_URL=https://staging.example.com

# JWT Authentication
JWT_SECRET_KEY=${SECRET:JWT_SECRET_KEY}  # From Key Vault
JWT_ISSUER=https://api-staging.example.com
JWT_AUDIENCE=https://staging.example.com
JWT_EXPIRATION_HOURS=8

# Redis (Managed Service)
REDIS_HOST=myproject-staging.redis.cache.windows.net
REDIS_PORT=6380
REDIS_PASSWORD=${SECRET:REDIS_PASSWORD}
REDIS_SSL=true

# External Services (Staging)
SMTP_HOST=smtp.sendgrid.net
SMTP_PORT=587
SMTP_USER=${SECRET:SMTP_USER}
SMTP_PASSWORD=${SECRET:SMTP_PASSWORD}
SMTP_FROM=staging@example.com

# Third-party APIs (Staging/Sandbox)
STRIPE_API_KEY=${SECRET:STRIPE_TEST_KEY}
STRIPE_WEBHOOK_SECRET=${SECRET:STRIPE_WEBHOOK_SECRET}

# Logging and Monitoring
LOG_LEVEL=Information
APPLICATIONINSIGHTS_CONNECTION_STRING=${SECRET:APPINSIGHTS_CONNECTION_STRING}
SENTRY_DSN=${SECRET:SENTRY_DSN}

# Feature Flags
FEATURE_USER_REGISTRATION=true
FEATURE_SOCIAL_LOGIN=true
FEATURE_ANALYTICS=true
FEATURE_BETA_FEATURES=true
```

### Kubernetes Configuration (if applicable)

**Namespace**: `myproject-staging`

**Deployment (`k8s/overlays/staging/deployment.yaml`)**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: backend
  namespace: myproject-staging
spec:
  replicas: 2
  selector:
    matchLabels:
      app: backend
      env: staging
  template:
    metadata:
      labels:
        app: backend
        env: staging
    spec:
      containers:
      - name: api
        image: myregistry.azurecr.io/myproject/backend:staging
        ports:
        - containerPort: 5000
        env:
        - name: ASPNETCORE_ENVIRONMENT
          value: "Staging"
        - name: ConnectionStrings__DefaultConnection
          valueFrom:
            secretKeyRef:
              name: database-secret
              key: connection-string
        resources:
          requests:
            memory: "512Mi"
            cpu: "250m"
          limits:
            memory: "1Gi"
            cpu: "500m"
        livenessProbe:
          httpGet:
            path: /health
            port: 5000
          initialDelaySeconds: 30
          periodSeconds: 10
        readinessProbe:
          httpGet:
            path: /health/ready
            port: 5000
          initialDelaySeconds: 10
          periodSeconds: 5
```

### Access URLs

| Service | URL | Access |
|---------|-----|--------|
| Frontend | https://staging.example.com | Public |
| Backend API | https://api-staging.example.com | Public |
| Swagger UI | https://api-staging.example.com/swagger | IP Restricted |
| Database | myproject-staging.postgres.database.azure.com:5432 | VPN Only |
| Redis | myproject-staging.redis.cache.windows.net:6380 | VPN Only |

### Resource Limits

```yaml
backend:
  replicas: 2
  resources:
    requests:
      cpu: 250m
      memory: 512Mi
    limits:
      cpu: 500m
      memory: 1Gi

frontend:
  replicas: 2
  resources:
    requests:
      cpu: 100m
      memory: 256Mi
    limits:
      cpu: 200m
      memory: 512Mi
```

### Security Configuration

**Staging Security (Production-Like)**:
- HTTPS: Required (TLS 1.2+)
- CORS: Restricted to staging domain
- Authentication: JWT with moderate expiration (8 hours)
- Rate Limiting: Enabled (relaxed: 1000 req/min)
- WAF: Enabled
- Secret Management: Azure Key Vault / AWS Secrets Manager
- Network: Private VNet with public endpoints
- IP Allowlisting: Swagger UI restricted to company IPs

---

## Production Environment

### Purpose

Live production environment serving real users.

### Infrastructure

**Hosting**: [Azure App Service / AWS ECS / Kubernetes cluster]  
**Region**: Primary: [e.g., East US], Secondary: [e.g., West US] (DR)  
**Scaling**: Auto-scaling (3-10 instances based on CPU/Memory)  
**High Availability**: Multi-zone deployment

**Services**:
- Backend API (containerized, 3+ replicas, auto-scaling)
- Frontend (CDN + containerized origin, 3+ replicas)
- PostgreSQL (managed service with read replicas)
- Redis (managed service with persistence and replication)
- Load Balancer (cloud provider managed, multi-zone)
- CDN (Azure CDN / CloudFront)
- WAF (Web Application Firewall)

### Configuration

#### Environment Variables

```bash
# Project
PROJECT_NAME=myproject
ENVIRONMENT=Production

# Database (Managed Service with Replication)
DATABASE_HOST=myproject-prod.postgres.database.azure.com
DATABASE_PORT=5432
DATABASE_NAME=myproject_production
DATABASE_USER=dbadmin@myproject-prod
DATABASE_PASSWORD=${SECRET:DATABASE_PASSWORD}  # From Key Vault
DATABASE_SSL_MODE=require
DATABASE_CONNECTION_POOL_SIZE=20
DATABASE_READ_REPLICA_HOST=myproject-prod-replica.postgres.database.azure.com

# Application
ASPNETCORE_ENVIRONMENT=Production
API_BASE_URL=https://api.example.com
FRONTEND_URL=https://www.example.com

# JWT Authentication
JWT_SECRET_KEY=${SECRET:JWT_SECRET_KEY}  # Rotated regularly
JWT_ISSUER=https://api.example.com
JWT_AUDIENCE=https://www.example.com
JWT_EXPIRATION_HOURS=2

# Redis (Managed Service with Clustering)
REDIS_HOST=myproject-prod.redis.cache.windows.net
REDIS_PORT=6380
REDIS_PASSWORD=${SECRET:REDIS_PASSWORD}
REDIS_SSL=true
REDIS_CLUSTER_MODE=enabled

# External Services (Production)
SMTP_HOST=smtp.sendgrid.net
SMTP_PORT=587
SMTP_USER=${SECRET:SMTP_USER}
SMTP_PASSWORD=${SECRET:SMTP_PASSWORD}
SMTP_FROM=noreply@example.com

# Third-party APIs (Production)
STRIPE_API_KEY=${SECRET:STRIPE_LIVE_KEY}
STRIPE_WEBHOOK_SECRET=${SECRET:STRIPE_WEBHOOK_SECRET_PROD}

# Logging and Monitoring
LOG_LEVEL=Warning
APPLICATIONINSIGHTS_CONNECTION_STRING=${SECRET:APPINSIGHTS_CONNECTION_STRING_PROD}
SENTRY_DSN=${SECRET:SENTRY_DSN_PROD}
DATADOG_API_KEY=${SECRET:DATADOG_API_KEY}

# CDN
CDN_URL=https://cdn.example.com

# Feature Flags
FEATURE_USER_REGISTRATION=true
FEATURE_SOCIAL_LOGIN=true
FEATURE_ANALYTICS=true
FEATURE_BETA_FEATURES=false
```

### Kubernetes Configuration (if applicable)

**Namespace**: `myproject-production`

**Deployment with HPA**:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: backend
  namespace: myproject-production
spec:
  replicas: 3
  strategy:
    type: RollingUpdate
    rollingUpdate:
      maxSurge: 1
      maxUnavailable: 0
  selector:
    matchLabels:
      app: backend
      env: production
  template:
    metadata:
      labels:
        app: backend
        env: production
    spec:
      affinity:
        podAntiAffinity:
          preferredDuringSchedulingIgnoredDuringExecution:
          - weight: 100
            podAffinityTerm:
              labelSelector:
                matchExpressions:
                - key: app
                  operator: In
                  values:
                  - backend
              topologyKey: kubernetes.io/hostname
      containers:
      - name: api
        image: myregistry.azurecr.io/myproject/backend:1.2.3
        ports:
        - containerPort: 5000
        env:
        - name: ASPNETCORE_ENVIRONMENT
          value: "Production"
        - name: ConnectionStrings__DefaultConnection
          valueFrom:
            secretKeyRef:
              name: database-secret-prod
              key: connection-string
        resources:
          requests:
            memory: "1Gi"
            cpu: "500m"
          limits:
            memory: "2Gi"
            cpu: "1000m"
        livenessProbe:
          httpGet:
            path: /health
            port: 5000
          initialDelaySeconds: 60
          periodSeconds: 10
          timeoutSeconds: 5
          failureThreshold: 3
        readinessProbe:
          httpGet:
            path: /health/ready
            port: 5000
          initialDelaySeconds: 30
          periodSeconds: 5
          timeoutSeconds: 3
          failureThreshold: 2
---
apiVersion: autoscaling/v2
kind: HorizontalPodAutoscaler
metadata:
  name: backend-hpa
  namespace: myproject-production
spec:
  scaleTargetRef:
    apiVersion: apps/v1
    kind: Deployment
    name: backend
  minReplicas: 3
  maxReplicas: 10
  metrics:
  - type: Resource
    resource:
      name: cpu
      target:
        type: Utilization
        averageUtilization: 70
  - type: Resource
    resource:
      name: memory
      target:
        type: Utilization
        averageUtilization: 80
```

### Access URLs

| Service | URL | Access |
|---------|-----|--------|
| Frontend | https://www.example.com | Public (CDN) |
| Backend API | https://api.example.com | Public (WAF protected) |
| Swagger UI | N/A | Disabled in production |
| Database | myproject-prod.postgres.database.azure.com:5432 | Private VNet Only |
| Redis | myproject-prod.redis.cache.windows.net:6380 | Private VNet Only |
| Admin Portal | https://admin.example.com | IP Restricted + MFA |

### Resource Limits

```yaml
backend:
  replicas: 3-10 (auto-scaling)
  resources:
    requests:
      cpu: 500m
      memory: 1Gi
    limits:
      cpu: 1000m
      memory: 2Gi

frontend:
  replicas: 3-6 (auto-scaling)
  resources:
    requests:
      cpu: 200m
      memory: 512Mi
    limits:
      cpu: 400m
      memory: 1Gi

database:
  tier: Premium (managed service)
  vCores: 4
  memory: 16GB
  storage: 500GB (auto-grow enabled)
  replicas: 1 read replica

redis:
  tier: Premium (managed service)
  memory: 6GB
  replicas: 2 (master + replica)
  persistence: RDB + AOF
```

### Security Configuration

**Production Security (Maximum)**:
- HTTPS: Required (TLS 1.3, strict cert validation)
- HSTS: Enabled (max-age=31536000)
- CORS: Restricted to production domain only
- Authentication: JWT with short expiration (2 hours) + refresh tokens
- Rate Limiting: Strict (100 req/min per IP)
- WAF: Enabled (OWASP Top 10 rules)
- DDoS Protection: Enabled
- Secret Management: Azure Key Vault with managed identities
- Network: Private VNet, no public database access
- Encryption: TLS in transit, AES-256 at rest
- IP Allowlisting: Admin endpoints restricted
- Security Headers: CSP, X-Frame-Options, X-Content-Type-Options
- MFA: Required for admin access
- Audit Logging: Enabled for all access

---

## CI/CD Configuration

### GitHub Actions (`.github/workflows/`)

**Environment Secrets**:
- Stored in GitHub Secrets
- Different secrets per environment
- Secrets injected at build/deploy time

**Staging Secrets**:
```
AZURE_CREDENTIALS_STAGING
DATABASE_PASSWORD_STAGING
JWT_SECRET_KEY_STAGING
REDIS_PASSWORD_STAGING
STRIPE_TEST_KEY
```

**Production Secrets**:
```
AZURE_CREDENTIALS_PRODUCTION
DATABASE_PASSWORD_PRODUCTION
JWT_SECRET_KEY_PRODUCTION
REDIS_PASSWORD_PRODUCTION
STRIPE_LIVE_KEY
```

### Deployment Pipeline

**Staging Deployment**:
- Trigger: Push to `main` branch
- Steps:
  1. Build Docker images
  2. Run tests
  3. Push to container registry
  4. Deploy to staging
  5. Run smoke tests
  6. Notify team

**Production Deployment**:
- Trigger: Tag with `v*` pattern (e.g., v1.2.3)
- Approval: Manual approval required
- Steps:
  1. Build Docker images
  2. Run full test suite
  3. Security scan
  4. Push to container registry
  5. **Manual approval gate**
  6. Deploy to production (blue-green)
  7. Run smoke tests
  8. Monitor for 15 minutes
  9. Auto-rollback if errors
  10. Notify team

---

## Monitoring & Logging

### Application Insights / CloudWatch / Datadog

**Metrics Collected**:
- Request rate, duration, errors
- Database query performance
- Cache hit rate
- Memory and CPU usage
- Custom business metrics

**Alerts**:
- Error rate > 1%
- Response time p95 > 1000ms
- CPU usage > 80%
- Memory usage > 90%
- Database connections > 80% of pool
- Disk space < 20%

### Logging Configuration

**Development**:
- Level: Debug
- Destination: Console
- Format: Human-readable

**Staging**:
- Level: Information
- Destination: Application Insights + File
- Format: JSON (structured)

**Production**:
- Level: Warning
- Destination: Application Insights + Sentry (errors)
- Format: JSON (structured)
- Retention: 90 days
- PII Filtering: Enabled

### Health Checks

**Endpoints**:
- `/health` - Basic health check
- `/health/ready` - Readiness check (includes dependencies)
- `/health/live` - Liveness check

**Checks**:
- Database connectivity
- Redis connectivity
- External API availability
- Disk space
- Memory availability

---

## Disaster Recovery

### Backup Strategy

**Database**:
- Automated daily backups (retained 30 days)
- Point-in-time restore (7 days)
- Geo-replicated backups

**Configuration**:
- All config in version control
- Secrets in Key Vault (backed up)

**Data**:
- User-uploaded files in blob storage (geo-redundant)

### Recovery Procedures

**RTO (Recovery Time Objective)**: 2 hours  
**RPO (Recovery Point Objective)**: 15 minutes

**Failover Steps**:
1. Declare incident
2. Assess damage
3. Failover to secondary region (if needed)
4. Restore from backup
5. Validate data integrity
6. Resume operations
7. Post-mortem

---

## Environment Comparison Matrix

| Aspect | Development | Staging | Production |
|--------|-------------|---------|------------|
| **Purpose** | Feature development | QA testing | Live users |
| **Data** | Synthetic | Anonymized production-like | Real user data |
| **Infrastructure** | Docker Compose (local) | Cloud (fixed scale) | Cloud (auto-scale) |
| **Security** | Relaxed | Production-like | Maximum |
| **HTTPS** | Optional | Required | Required |
| **Authentication** | Long expiry (24h) | Medium (8h) | Short (2h) |
| **Rate Limiting** | Disabled | Relaxed | Strict |
| **Logging** | Debug | Information | Warning+ |
| **Monitoring** | None | Basic | Comprehensive |
| **Backups** | None | Daily | Continuous |
| **Cost** | $0 | ~$500/month | ~$2000/month |
| **Deployment** | Manual | Auto (on main) | Manual (on tag + approval) |

---

## Troubleshooting

### Common Issues

**Database Connection Failed**:
```bash
# Check connection string
echo $ConnectionStrings__DefaultConnection

# Test connection
psql -h database -U postgres -d appdb

# Check database service
docker-compose ps database
docker-compose logs database
```

**Redis Connection Failed**:
```bash
# Check Redis is running
docker-compose ps cache
docker-compose logs cache

# Test connection
redis-cli -h localhost -p 6379 ping
```

**Docker Build Failed**:
```bash
# Clean Docker cache
docker system prune -a

# Rebuild with no cache
docker-compose build --no-cache

# Check Dockerfile syntax
docker build -f infrastructure/docker/backend.Dockerfile .
```

**Environment Variables Not Loading**:
```bash
# Check .env file exists
ls -la .env

# Check Docker Compose reads .env
docker-compose config

# Verify variables inside container
docker-compose exec backend env | grep DATABASE
```

---

## Validation Checklist

- [ ] All environment variables documented
- [ ] Secrets stored securely (Key Vault, not in code)
- [ ] Docker containers build successfully
- [ ] Health checks configured and passing
- [ ] Resource limits appropriate for workload
- [ ] Security configurations match environment
- [ ] Monitoring and alerting configured
- [ ] Backup and restore tested
- [ ] Disaster recovery plan documented
- [ ] Access URLs documented and accessible
- [ ] CI/CD pipelines deploy successfully
- [ ] Environment parity maintained (dev/staging/prod)

---

## Maintenance

### Regular Updates

**Monthly**:
- Review and rotate production secrets
- Update base Docker images
- Review resource utilization and adjust limits
- Check security vulnerabilities

**Quarterly**:
- Disaster recovery drill
- Review and update monitoring alerts
- Optimize costs
- Update documentation

### Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | [Date] | Initial configuration | [Name] |

---

*This environment configuration is the authoritative reference for all environment settings. Any changes must be reviewed and approved by DevOps team.*
