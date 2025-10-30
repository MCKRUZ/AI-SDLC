# Repository Setup Workflow

## Purpose

This workflow guides you through the systematic process of establishing complete development infrastructure, from repository initialization through CI/CD pipeline configuration. The output is a fully functional development environment where the entire team can immediately begin feature development.

**What This Workflow Accomplishes**:
- Initializes Git repository with proper structure and conventions
- Establishes branch strategy and protection rules
- Configures CI/CD pipeline for automated build, test, and deploy
- Sets up local development environment (Docker-based)
- Provisions database with migration framework
- Implements authentication/authorization framework
- Configures logging, monitoring, and observability
- Establishes code quality standards (linting, formatting)
- Sets up test framework and coverage reporting
- Creates project documentation structure

**What This Workflow Does NOT Do**:
- Implement business features (that's Phase 3)
- Make architecture decisions (that's Phase 1)
- Define requirements (that's Phase 0)
- Plan sprints (that's sprint planning workflow)

---

## Prerequisites

### Required Inputs

Before starting, ensure you have:

- [ ] **Architecture Document** (`architecture.md`) - Technical design and component structure
- [ ] **Technology Stack Decision** - Languages, frameworks, databases chosen
- [ ] **Constitution** (`constitution.md`) - Quality standards and constraints
- [ ] **Access to Infrastructure**:
  - [ ] Source control platform (GitHub, GitLab, Azure DevOps, etc.)
  - [ ] CI/CD platform (GitHub Actions, Azure Pipelines, Jenkins, etc.)
  - [ ] Cloud provider (Azure, AWS, GCP) or on-premises servers
  - [ ] Container registry (if using Docker)
  - [ ] Package/artifact repository
- [ ] **Team Accounts Created**:
  - [ ] All developers have access to source control
  - [ ] All developers have access to CI/CD platform
  - [ ] All developers have access to cloud resources (if applicable)
- [ ] **Secrets and Credentials**:
  - [ ] Database connection strings
  - [ ] API keys for external services
  - [ ] Cloud service credentials
  - [ ] Certificate files (if needed)

### Agent Setup

You should be in **DevOps Scaffolder Agent** mode with all context loaded:

```markdown
You are the DevOps Scaffolder Agent, an expert in infrastructure setup, 
CI/CD pipelines, containerization, and development environment configuration.

Context loaded:
- Architecture.md (technical design)
- Constitution.md (quality standards)
- Technology stack decisions

Your mission: Establish complete development infrastructure that enables 
the team to start feature development on Day 1 of Sprint 1.

Ready to begin repository setup.
```

---

## Workflow Steps

### Step 0: Pre-Setup Validation (30 minutes)

#### Objective
Ensure all prerequisites are met before beginning setup.

#### Actions

**0.1 Validate Access and Permissions**

```markdown
## Access Validation Checklist

**Source Control**:
- [ ] Repository can be created in the organization
- [ ] All team members added to organization
- [ ] Admin access configured for DevOps lead

**CI/CD Platform**:
- [ ] Build agents available or can be provisioned
- [ ] Service connections configured (cloud provider, container registry)
- [ ] Secrets management available

**Cloud/Infrastructure**:
- [ ] Resource groups/projects created
- [ ] Billing configured and approved
- [ ] Network/firewall rules documented
- [ ] Naming conventions defined

**Credentials Secured**:
- [ ] All secrets documented in secure vault
- [ ] Team leads have access to secrets
- [ ] Rotation policy defined
```

**0.2 Review Technology Stack**

From architecture document, confirm:

```markdown
## Technology Stack Summary

**Frontend**:
- Framework: [React, Angular, Vue, etc.]
- Language: [TypeScript, JavaScript]
- Build tool: [Vite, Webpack, etc.]
- Package manager: [npm, yarn, pnpm]

**Backend**:
- Framework: [ASP.NET Core, Node.js, Django, etc.]
- Language: [C#, TypeScript, Python, etc.]
- Runtime: [.NET 8, Node 20, Python 3.12, etc.]

**Database**:
- Type: [SQL Server, PostgreSQL, MongoDB, etc.]
- Version: [Specific version]
- Migration tool: [EF Core Migrations, Flyway, Alembic, etc.]

**Infrastructure**:
- Container platform: [Docker, Podman]
- Orchestration: [Docker Compose, Kubernetes, none]
- Cloud provider: [Azure, AWS, GCP, on-premises]

**Tools**:
- Linting: [ESLint, StyleCop, etc.]
- Formatting: [Prettier, EditorConfig]
- Testing: [xUnit, Jest, Pytest, etc.]
- Coverage: [Coverlet, Istanbul, Coverage.py]
```

**Output**: Validated access and confirmed technology stack

---

### Step 1: Initialize Repository Structure (1-2 hours)

#### Objective
Create Git repository with proper directory structure and foundational files.

#### Actions

**1.1 Create Repository**

```bash
# Create repository in your source control platform
# Repository name should follow convention: [org]-[project-name]
# Example: acme-customer-portal

# Clone repository locally
git clone https://[platform]/[org]/[project-name].git
cd [project-name]

# Set up initial branch structure
git checkout -b develop
git push -u origin develop
```

**1.2 Create Directory Structure**

Based on architecture and technology stack:

```markdown
## Repository Structure

### For Monorepo (Frontend + Backend together):

```
project-root/
├── .github/                    # GitHub-specific (or .gitlab, .azuredevops)
│   ├── workflows/              # CI/CD pipeline definitions
│   ├── PULL_REQUEST_TEMPLATE.md
│   └── ISSUE_TEMPLATE/
├── docs/                       # Project documentation
│   ├── architecture/           # Architecture decision records (ADRs)
│   ├── api/                    # API documentation
│   ├── setup/                  # Setup guides
│   └── contributing.md         # Contribution guidelines
├── src/
│   ├── frontend/               # Frontend application
│   │   ├── src/
│   │   ├── public/
│   │   ├── tests/
│   │   ├── package.json
│   │   ├── tsconfig.json
│   │   ├── .eslintrc.json
│   │   └── vite.config.ts
│   ├── backend/                # Backend application
│   │   ├── [ProjectName].Api/
│   │   ├── [ProjectName].Core/
│   │   ├── [ProjectName].Infrastructure/
│   │   ├── [ProjectName].Tests/
│   │   └── [ProjectName].sln
│   └── shared/                 # Shared code/types
├── infrastructure/             # Infrastructure as Code
│   ├── docker/
│   │   ├── Dockerfile.frontend
│   │   ├── Dockerfile.backend
│   │   └── docker-compose.yml
│   ├── terraform/              # Or bicep, ARM templates
│   └── kubernetes/             # If using K8s
├── scripts/                    # Build, deployment, utility scripts
│   ├── setup-dev-env.sh
│   ├── run-tests.sh
│   ├── deploy.sh
│   └── seed-data.sh
├── .editorconfig              # Editor configuration
├── .gitignore                 # Git ignore rules
├── .gitattributes             # Git attributes
├── README.md                  # Project overview
├── CHANGELOG.md               # Change log
├── LICENSE                    # License file
└── docker-compose.yml         # Local development setup
```

### For Separate Repositories (Frontend + Backend separate):

**Frontend Repository Structure:**
```
frontend-repo/
├── .github/workflows/
├── docs/
├── src/
├── public/
├── tests/
├── .eslintrc.json
├── .prettierrc
├── package.json
├── tsconfig.json
├── vite.config.ts
├── .env.example
└── README.md
```

**Backend Repository Structure:**
```
backend-repo/
├── .github/workflows/
├── docs/
├── src/
│   ├── [ProjectName].Api/
│   ├── [ProjectName].Core/
│   ├── [ProjectName].Infrastructure/
│   └── [ProjectName].Tests/
├── infrastructure/
├── scripts/
├── .editorconfig
├── [ProjectName].sln
└── README.md
```
```

**1.3 Create Foundational Files**

Create the following key files:

**README.md**:
```markdown
# [Project Name]

[Brief description of the project]

## Prerequisites

- [List required software and versions]
- [Docker Desktop or Docker Engine]
- [IDE recommendations]

## Getting Started

### Local Development Setup

1. Clone the repository
2. Run setup script: `./scripts/setup-dev-env.sh`
3. Start services: `docker-compose up`
4. Access application: http://localhost:[port]

### Running Tests

```bash
# Run all tests
./scripts/run-tests.sh

# Run specific test suite
npm test                     # Frontend
dotnet test                  # Backend
```

### Code Quality

```bash
# Lint code
npm run lint                 # Frontend
dotnet format --verify-no-changes  # Backend

# Format code
npm run format               # Frontend
dotnet format                # Backend
```

## Architecture

See [docs/architecture/README.md](docs/architecture/README.md)

## Contributing

See [docs/contributing.md](docs/contributing.md)

## License

[License type]
```

**.gitignore**:
Create appropriate .gitignore for your tech stack:
```gitignore
# Common
.env
.env.local
*.log
node_modules/
.DS_Store
.vscode/
.idea/

# .NET
bin/
obj/
*.user
*.suo

# Frontend
dist/
build/
.parcel-cache/
coverage/

# Database
*.db
*.db-shm
*.db-wal

# Docker
docker-compose.override.yml

# Secrets
secrets/
*.key
*.pem
*.crt
```

**.editorconfig**:
```ini
root = true

[*]
indent_style = space
indent_size = 2
end_of_line = lf
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true

[*.cs]
indent_size = 4

[*.md]
trim_trailing_whitespace = false

[*.{yml,yaml}]
indent_size = 2
```

**1.4 Commit Initial Structure**

```bash
git add .
git commit -m "chore: initialize repository structure"
git push origin develop
```

**Output**: Repository with proper structure and foundational files

---

### Step 2: Configure Branch Strategy and Protection (30 minutes)

#### Objective
Establish branching model and protect critical branches.

#### Actions

**2.1 Define Branch Strategy**

```markdown
## Branch Strategy

**Main Branches**:
- `main` - Production-ready code, deployed to production
- `develop` - Integration branch, deployed to staging/dev environment

**Supporting Branches**:
- `feature/*` - New features (e.g., feature/user-authentication)
- `bugfix/*` - Bug fixes for develop (e.g., bugfix/login-error)
- `hotfix/*` - Urgent production fixes (e.g., hotfix/security-patch)
- `release/*` - Release preparation (e.g., release/v1.2.0)

**Branch Lifecycle**:
1. Create feature branch from `develop`
2. Implement feature with commits
3. Create pull request to `develop`
4. Code review and approval required
5. Merge to `develop` after CI passes
6. Delete feature branch after merge

**Release Process**:
1. Create `release/*` branch from `develop`
2. Final testing and bug fixes
3. Merge to `main` and tag with version
4. Merge back to `develop`
5. Deploy `main` to production
```

**2.2 Configure Branch Protection Rules**

For `main` branch:
```markdown
## Main Branch Protection

- [ ] Require pull request before merging
- [ ] Require at least 2 approvals
- [ ] Require review from code owners
- [ ] Dismiss stale approvals when new commits pushed
- [ ] Require status checks to pass:
  - [ ] Build succeeds
  - [ ] All tests pass
  - [ ] Code coverage ≥80%
  - [ ] Linting passes
  - [ ] Security scan passes
- [ ] Require branches to be up to date
- [ ] Require conversation resolution before merging
- [ ] Restrict who can push to main (admins only)
- [ ] Require linear history (no merge commits)
```

For `develop` branch:
```markdown
## Develop Branch Protection

- [ ] Require pull request before merging
- [ ] Require at least 1 approval
- [ ] Require status checks to pass:
  - [ ] Build succeeds
  - [ ] All tests pass
  - [ ] Linting passes
- [ ] Require branches to be up to date
```

**2.3 Create Pull Request Template**

Create `.github/PULL_REQUEST_TEMPLATE.md`:

```markdown
## Description

[Describe what this PR changes and why]

## Type of Change

- [ ] Bug fix (non-breaking change which fixes an issue)
- [ ] New feature (non-breaking change which adds functionality)
- [ ] Breaking change (fix or feature that would cause existing functionality to not work as expected)
- [ ] Documentation update
- [ ] Code refactoring
- [ ] Performance improvement
- [ ] Test addition/update

## Related Issues

Closes #[issue number]

## Testing

### Test Coverage
- [ ] Unit tests added/updated
- [ ] Integration tests added/updated
- [ ] Manual testing completed

### Test Scenarios
[Describe key test scenarios and results]

## Checklist

- [ ] My code follows the project's code style guidelines
- [ ] I have performed a self-review of my own code
- [ ] I have commented my code, particularly in hard-to-understand areas
- [ ] I have made corresponding changes to the documentation
- [ ] My changes generate no new warnings
- [ ] I have added tests that prove my fix is effective or that my feature works
- [ ] New and existing unit tests pass locally with my changes
- [ ] Any dependent changes have been merged and published

## Screenshots (if applicable)

[Add screenshots here]

## Additional Notes

[Any additional information that reviewers should know]
```

**Output**: Branch strategy defined and protection rules configured

---

### Step 3: Set Up CI/CD Pipeline (2-4 hours)

#### Objective
Configure automated build, test, and deployment pipeline.

#### Actions

**3.1 Create CI/CD Pipeline Configuration**

For GitHub Actions (`.github/workflows/ci.yml`):

```yaml
name: CI/CD Pipeline

on:
  push:
    branches: [ main, develop ]
  pull_request:
    branches: [ main, develop ]

env:
  NODE_VERSION: '20.x'
  DOTNET_VERSION: '8.0.x'

jobs:
  # Frontend Build and Test
  frontend:
    name: Frontend CI
    runs-on: ubuntu-latest
    defaults:
      run:
        working-directory: ./src/frontend
    
    steps:
    - uses: actions/checkout@v4
    
    - name: Setup Node.js
      uses: actions/setup-node@v4
      with:
        node-version: ${{ env.NODE_VERSION }}
        cache: 'npm'
        cache-dependency-path: './src/frontend/package-lock.json'
    
    - name: Install dependencies
      run: npm ci
    
    - name: Lint
      run: npm run lint
    
    - name: Type check
      run: npm run type-check
    
    - name: Run tests
      run: npm run test:ci
    
    - name: Build
      run: npm run build
    
    - name: Upload coverage
      uses: codecov/codecov-action@v3
      with:
        files: ./src/frontend/coverage/lcov.info
        flags: frontend
    
    - name: Upload build artifacts
      uses: actions/upload-artifact@v4
      with:
        name: frontend-dist
        path: ./src/frontend/dist

  # Backend Build and Test
  backend:
    name: Backend CI
    runs-on: ubuntu-latest
    defaults:
      run:
        working-directory: ./src/backend
    
    steps:
    - uses: actions/checkout@v4
    
    - name: Setup .NET
      uses: actions/setup-dotnet@v4
      with:
        dotnet-version: ${{ env.DOTNET_VERSION }}
    
    - name: Restore dependencies
      run: dotnet restore
    
    - name: Build
      run: dotnet build --configuration Release --no-restore
    
    - name: Run tests
      run: dotnet test --configuration Release --no-build --verbosity normal --collect:"XPlat Code Coverage"
    
    - name: Upload coverage
      uses: codecov/codecov-action@v3
      with:
        files: ./src/backend/**/coverage.cobertura.xml
        flags: backend
    
    - name: Publish
      run: dotnet publish --configuration Release --no-build --output ./publish
    
    - name: Upload publish artifacts
      uses: actions/upload-artifact@v4
      with:
        name: backend-publish
        path: ./src/backend/publish

  # Security Scanning
  security:
    name: Security Scan
    runs-on: ubuntu-latest
    
    steps:
    - uses: actions/checkout@v4
    
    - name: Run Trivy vulnerability scanner
      uses: aquasecurity/trivy-action@master
      with:
        scan-type: 'fs'
        scan-ref: '.'
        format: 'sarif'
        output: 'trivy-results.sarif'
    
    - name: Upload Trivy results to GitHub Security
      uses: github/codeql-action/upload-sarif@v3
      with:
        sarif_file: 'trivy-results.sarif'

  # Docker Build
  docker:
    name: Build Docker Images
    runs-on: ubuntu-latest
    needs: [frontend, backend]
    if: github.event_name == 'push'
    
    steps:
    - uses: actions/checkout@v4
    
    - name: Download frontend artifacts
      uses: actions/download-artifact@v4
      with:
        name: frontend-dist
        path: ./src/frontend/dist
    
    - name: Download backend artifacts
      uses: actions/download-artifact@v4
      with:
        name: backend-publish
        path: ./src/backend/publish
    
    - name: Set up Docker Buildx
      uses: docker/setup-buildx-action@v3
    
    - name: Login to Container Registry
      uses: docker/login-action@v3
      with:
        registry: ${{ secrets.CONTAINER_REGISTRY }}
        username: ${{ secrets.REGISTRY_USERNAME }}
        password: ${{ secrets.REGISTRY_PASSWORD }}
    
    - name: Build and push Frontend image
      uses: docker/build-push-action@v5
      with:
        context: ./src/frontend
        file: ./infrastructure/docker/Dockerfile.frontend
        push: true
        tags: ${{ secrets.CONTAINER_REGISTRY }}/frontend:${{ github.sha }}
        cache-from: type=gha
        cache-to: type=gha,mode=max
    
    - name: Build and push Backend image
      uses: docker/build-push-action@v5
      with:
        context: ./src/backend
        file: ./infrastructure/docker/Dockerfile.backend
        push: true
        tags: ${{ secrets.CONTAINER_REGISTRY }}/backend:${{ github.sha }}
        cache-from: type=gha
        cache-to: type=gha,mode=max

  # Deploy to Dev Environment
  deploy-dev:
    name: Deploy to Dev
    runs-on: ubuntu-latest
    needs: [docker]
    if: github.ref == 'refs/heads/develop' && github.event_name == 'push'
    environment:
      name: development
      url: https://dev.example.com
    
    steps:
    - uses: actions/checkout@v4
    
    - name: Deploy to Dev Environment
      run: |
        # Add deployment commands here
        # Examples: kubectl apply, helm upgrade, terraform apply
        echo "Deploying to dev environment..."
    
    - name: Run smoke tests
      run: |
        # Run basic health checks
        curl -f https://dev.example.com/health || exit 1

  # Deploy to Production
  deploy-prod:
    name: Deploy to Production
    runs-on: ubuntu-latest
    needs: [docker]
    if: github.ref == 'refs/heads/main' && github.event_name == 'push'
    environment:
      name: production
      url: https://www.example.com
    
    steps:
    - uses: actions/checkout@v4
    
    - name: Deploy to Production
      run: |
        # Add production deployment commands
        echo "Deploying to production..."
    
    - name: Run smoke tests
      run: |
        curl -f https://www.example.com/health || exit 1
    
    - name: Create release
      uses: actions/create-release@v1
      env:
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
      with:
        tag_name: v${{ github.run_number }}
        release_name: Release v${{ github.run_number }}
        draft: false
        prerelease: false
```

**3.2 Configure Pipeline Secrets**

Add required secrets to your CI/CD platform:

```markdown
## Required Secrets

**Container Registry**:
- `CONTAINER_REGISTRY` - Registry URL (e.g., acr.azurecr.io)
- `REGISTRY_USERNAME` - Registry username
- `REGISTRY_PASSWORD` - Registry password

**Cloud Provider**:
- `AZURE_CREDENTIALS` (or AWS_ACCESS_KEY_ID, GCP_SA_KEY)
- `AZURE_SUBSCRIPTION_ID`

**Database**:
- `DB_CONNECTION_STRING_DEV`
- `DB_CONNECTION_STRING_PROD`

**Application Secrets**:
- `JWT_SECRET_KEY`
- `API_ENCRYPTION_KEY`

**Third-Party Services**:
- `SENDGRID_API_KEY` (if using email)
- `STRIPE_API_KEY` (if using payments)
- [Add others as needed]

**Code Quality**:
- `CODECOV_TOKEN` (if using Codecov)
```

**3.3 Test CI/CD Pipeline**

```bash
# Create test branch
git checkout -b test/ci-pipeline

# Make a small change to trigger pipeline
echo "# Test" >> README.md
git add README.md
git commit -m "test: trigger CI pipeline"
git push origin test/ci-pipeline

# Create pull request and verify:
# - All jobs run successfully
# - Tests pass
# - Coverage reports generated
# - Security scans complete
# - Build artifacts created
```

**Output**: Fully functional CI/CD pipeline with automated testing and deployment

---

### Step 4: Configure Local Development Environment (2-3 hours)

#### Objective
Set up containerized local development environment that works for all team members.

#### Actions

**4.1 Create Docker Compose Configuration**

Create `docker-compose.yml`:

```yaml
version: '3.8'

services:
  # Database
  database:
    image: postgres:16-alpine  # Or mcr.microsoft.com/mssql/server:2022-latest for SQL Server
    container_name: ${PROJECT_NAME:-app}-db
    environment:
      POSTGRES_USER: ${DB_USER:-devuser}
      POSTGRES_PASSWORD: ${DB_PASSWORD:-devpassword}
      POSTGRES_DB: ${DB_NAME:-appdb}
    ports:
      - "5432:5432"
    volumes:
      - db-data:/var/lib/postgresql/data
      - ./scripts/seed-data.sql:/docker-entrypoint-initdb.d/seed-data.sql
    networks:
      - app-network
    healthcheck:
      test: ["CMD-SHELL", "pg_isready -U ${DB_USER:-devuser}"]
      interval: 10s
      timeout: 5s
      retries: 5

  # Backend API
  backend:
    build:
      context: ./src/backend
      dockerfile: ../../infrastructure/docker/Dockerfile.backend.dev
    container_name: ${PROJECT_NAME:-app}-backend
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ConnectionStrings__DefaultConnection=Host=database;Database=${DB_NAME:-appdb};Username=${DB_USER:-devuser};Password=${DB_PASSWORD:-devpassword}
      - JWT__Secret=${JWT_SECRET:-dev-secret-key-change-in-production}
      - JWT__Issuer=http://localhost:5000
      - JWT__Audience=http://localhost:5000
      - Logging__LogLevel__Default=Information
    ports:
      - "5000:80"
      - "5001:443"
    volumes:
      - ./src/backend:/app
      - /app/bin
      - /app/obj
    depends_on:
      database:
        condition: service_healthy
    networks:
      - app-network
    command: dotnet watch run --no-launch-profile

  # Frontend
  frontend:
    build:
      context: ./src/frontend
      dockerfile: ../../infrastructure/docker/Dockerfile.frontend.dev
    container_name: ${PROJECT_NAME:-app}-frontend
    environment:
      - VITE_API_BASE_URL=http://localhost:5000
      - VITE_APP_NAME=${PROJECT_NAME:-App}
    ports:
      - "3000:3000"
    volumes:
      - ./src/frontend:/app
      - /app/node_modules
    depends_on:
      - backend
    networks:
      - app-network
    command: npm run dev -- --host

  # Redis (for caching, if needed)
  redis:
    image: redis:7-alpine
    container_name: ${PROJECT_NAME:-app}-redis
    ports:
      - "6379:6379"
    volumes:
      - redis-data:/data
    networks:
      - app-network
    healthcheck:
      test: ["CMD", "redis-cli", "ping"]
      interval: 10s
      timeout: 5s
      retries: 5

  # Mailhog (for email testing)
  mailhog:
    image: mailhog/mailhog:latest
    container_name: ${PROJECT_NAME:-app}-mailhog
    ports:
      - "1025:1025"  # SMTP
      - "8025:8025"  # Web UI
    networks:
      - app-network

volumes:
  db-data:
  redis-data:

networks:
  app-network:
    driver: bridge
```

**4.2 Create Development Dockerfiles**

Create `infrastructure/docker/Dockerfile.backend.dev`:

```dockerfile
FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR /app

# Copy solution and project files
COPY *.sln ./
COPY */*.csproj ./
RUN for file in $(ls *.csproj); do mkdir -p ${file%.*}/ && mv $file ${file%.*}/; done

# Restore dependencies
RUN dotnet restore

# Copy source code
COPY . ./

# Install dotnet-ef for migrations
RUN dotnet tool install --global dotnet-ef
ENV PATH="${PATH}:/root/.dotnet/tools"

EXPOSE 80
EXPOSE 443

# Default command
CMD ["dotnet", "watch", "run", "--project", "./[ProjectName].Api", "--no-launch-profile"]
```

Create `infrastructure/docker/Dockerfile.frontend.dev`:

```dockerfile
FROM node:20-alpine
WORKDIR /app

# Copy package files
COPY package*.json ./

# Install dependencies
RUN npm ci

# Copy source code
COPY . ./

EXPOSE 3000

# Default command
CMD ["npm", "run", "dev", "--", "--host"]
```

**4.3 Create Environment Configuration**

Create `.env.example`:

```env
# Project
PROJECT_NAME=myapp

# Database
DB_USER=devuser
DB_PASSWORD=devpassword
DB_NAME=appdb

# Backend
JWT_SECRET=dev-secret-key-change-in-production
JWT_ISSUER=http://localhost:5000
JWT_AUDIENCE=http://localhost:5000

# Frontend
VITE_API_BASE_URL=http://localhost:5000
VITE_APP_NAME=MyApp

# External Services (Development)
SENDGRID_API_KEY=your-key-here
STRIPE_API_KEY=your-key-here
```

**4.4 Create Setup Script**

Create `scripts/setup-dev-env.sh`:

```bash
#!/bin/bash

echo "Setting up development environment..."

# Check prerequisites
command -v docker >/dev/null 2>&1 || { echo "Docker is required but not installed. Aborting." >&2; exit 1; }
command -v docker-compose >/dev/null 2>&1 || { echo "Docker Compose is required but not installed. Aborting." >&2; exit 1; }

# Copy environment file if it doesn't exist
if [ ! -f .env ]; then
    echo "Creating .env file from .env.example..."
    cp .env.example .env
    echo "⚠️  Please update .env with your configuration"
fi

# Build and start services
echo "Building Docker containers..."
docker-compose build

echo "Starting services..."
docker-compose up -d

# Wait for database to be ready
echo "Waiting for database to be ready..."
sleep 10

# Run database migrations
echo "Running database migrations..."
docker-compose exec backend dotnet ef database update

# Seed initial data
echo "Seeding database..."
docker-compose exec backend dotnet run --project ./[ProjectName].Api -- --seed

echo "✅ Development environment setup complete!"
echo ""
echo "Services running:"
echo "  - Frontend: http://localhost:3000"
echo "  - Backend API: http://localhost:5000"
echo "  - Database: localhost:5432"
echo "  - Mailhog UI: http://localhost:8025"
echo ""
echo "To stop services: docker-compose down"
echo "To view logs: docker-compose logs -f"
echo "To rebuild: docker-compose up -d --build"
```

Make it executable:
```bash
chmod +x scripts/setup-dev-env.sh
```

**4.5 Test Local Environment**

```bash
# Run setup script
./scripts/setup-dev-env.sh

# Verify all services are running
docker-compose ps

# Test backend health endpoint
curl http://localhost:5000/health

# Test frontend loads
curl http://localhost:3000

# View logs
docker-compose logs -f
```

**Output**: Fully functional local development environment

---

### Step 5: Set Up Database and Migrations (1-2 hours)

#### Objective
Configure database with schema and migration framework.

#### Actions

**5.1 Initialize Migration Framework**

For Entity Framework Core (.NET):

```bash
# Navigate to backend project
cd src/backend/[ProjectName].Api

# Install EF Core tools
dotnet tool install --global dotnet-ef

# Create initial migration
dotnet ef migrations add InitialCreate --project ../[ProjectName].Infrastructure

# Apply migration
dotnet ef database update
```

For Node.js with TypeORM:

```bash
# Navigate to backend
cd src/backend

# Initialize TypeORM
npm install typeorm @nestjs/typeorm pg

# Create initial migration
npm run typeorm migration:create -- -n InitialMigration

# Run migrations
npm run typeorm migration:run
```

**5.2 Create Database Context**

For .NET (Entity Framework Core):

Create `src/backend/[ProjectName].Infrastructure/Data/ApplicationDbContext.cs`:

```csharp
using Microsoft.EntityFrameworkCore;
using [ProjectName].Core.Entities;

namespace [ProjectName].Infrastructure.Data
{
    public class ApplicationDbContext : DbContext
    {
        public ApplicationDbContext(DbContextOptions<ApplicationDbContext> options)
            : base(options)
        {
        }

        // DbSets
        public DbSet<User> Users { get; set; }
        public DbSet<Role> Roles { get; set; }
        // Add other entities

        protected override void OnModelCreating(ModelBuilder modelBuilder)
        {
            base.OnModelCreating(modelBuilder);

            // Apply all configurations from current assembly
            modelBuilder.ApplyConfigurationsFromAssembly(typeof(ApplicationDbContext).Assembly);

            // Seed initial data
            SeedData(modelBuilder);
        }

        private void SeedData(ModelBuilder modelBuilder)
        {
            // Seed roles
            modelBuilder.Entity<Role>().HasData(
                new Role { Id = 1, Name = "Admin", NormalizedName = "ADMIN" },
                new Role { Id = 2, Name = "User", NormalizedName = "USER" }
            );

            // Add other seed data
        }
    }
}
```

**5.3 Create Entity Configurations**

Create `src/backend/[ProjectName].Infrastructure/Data/Configurations/UserConfiguration.cs`:

```csharp
using Microsoft.EntityFrameworkCore;
using Microsoft.EntityFrameworkCore.Metadata.Builders;
using [ProjectName].Core.Entities;

namespace [ProjectName].Infrastructure.Data.Configurations
{
    public class UserConfiguration : IEntityTypeConfiguration<User>
    {
        public void Configure(EntityTypeBuilder<User> builder)
        {
            builder.ToTable("Users");

            builder.HasKey(u => u.Id);

            builder.Property(u => u.Email)
                .IsRequired()
                .HasMaxLength(255);

            builder.HasIndex(u => u.Email)
                .IsUnique();

            builder.Property(u => u.FirstName)
                .IsRequired()
                .HasMaxLength(100);

            builder.Property(u => u.LastName)
                .IsRequired()
                .HasMaxLength(100);

            builder.Property(u => u.CreatedAt)
                .IsRequired()
                .HasDefaultValueSql("GETUTCDATE()"); // Or NOW() for PostgreSQL

            // Add other configurations
        }
    }
}
```

**5.4 Create Seed Data Script**

Create `scripts/seed-data.sql`:

```sql
-- Seed initial data for development
-- This runs automatically when database container starts

-- Create initial admin user (password: Admin123!)
INSERT INTO "Users" ("Id", "Email", "FirstName", "LastName", "PasswordHash", "CreatedAt")
VALUES 
    (1, 'admin@example.com', 'Admin', 'User', '$2a$11$...', NOW())
ON CONFLICT DO NOTHING;

-- Assign admin role
INSERT INTO "UserRoles" ("UserId", "RoleId")
VALUES (1, 1)
ON CONFLICT DO NOTHING;

-- Add sample data for development
INSERT INTO [YourEntity] (...)
VALUES (...)
ON CONFLICT DO NOTHING;
```

**Output**: Database with schema, migrations, and seed data

---

### Step 6: Implement Authentication Framework (2-3 hours)

#### Objective
Set up JWT-based authentication and authorization framework.

#### Actions

**6.1 Configure JWT Authentication**

For .NET, update `src/backend/[ProjectName].Api/Program.cs`:

```csharp
using Microsoft.AspNetCore.Authentication.JwtBearer;
using Microsoft.IdentityModel.Tokens;
using System.Text;

var builder = WebApplication.CreateBuilder(args);

// Add JWT Authentication
builder.Services.AddAuthentication(options =>
{
    options.DefaultAuthenticateScheme = JwtBearerDefaults.AuthenticationScheme;
    options.DefaultChallengeScheme = JwtBearerDefaults.AuthenticationScheme;
})
.AddJwtBearer(options =>
{
    options.TokenValidationParameters = new TokenValidationParameters
    {
        ValidateIssuer = true,
        ValidateAudience = true,
        ValidateLifetime = true,
        ValidateIssuerSigningKey = true,
        ValidIssuer = builder.Configuration["JWT:Issuer"],
        ValidAudience = builder.Configuration["JWT:Audience"],
        IssuerSigningKey = new SymmetricSecurityKey(
            Encoding.UTF8.GetBytes(builder.Configuration["JWT:Secret"]))
    };
});

builder.Services.AddAuthorization(options =>
{
    options.AddPolicy("AdminOnly", policy => policy.RequireRole("Admin"));
    options.AddPolicy("UserOrAdmin", policy => policy.RequireRole("User", "Admin"));
});

var app = builder.Build();

app.UseAuthentication();
app.UseAuthorization();

app.MapControllers();

app.Run();
```

**6.2 Create JWT Service**

Create `src/backend/[ProjectName].Infrastructure/Services/JwtService.cs`:

```csharp
using Microsoft.Extensions.Configuration;
using Microsoft.IdentityModel.Tokens;
using System;
using System.Collections.Generic;
using System.IdentityModel.Tokens.Jwt;
using System.Security.Claims;
using System.Text;

namespace [ProjectName].Infrastructure.Services
{
    public interface IJwtService
    {
        string GenerateToken(int userId, string email, IEnumerable<string> roles);
        ClaimsPrincipal? ValidateToken(string token);
    }

    public class JwtService : IJwtService
    {
        private readonly IConfiguration _configuration;
        private readonly SymmetricSecurityKey _key;

        public JwtService(IConfiguration configuration)
        {
            _configuration = configuration;
            _key = new SymmetricSecurityKey(
                Encoding.UTF8.GetBytes(_configuration["JWT:Secret"]));
        }

        public string GenerateToken(int userId, string email, IEnumerable<string> roles)
        {
            var claims = new List<Claim>
            {
                new Claim(ClaimTypes.NameIdentifier, userId.ToString()),
                new Claim(ClaimTypes.Email, email),
                new Claim(JwtRegisteredClaimNames.Jti, Guid.NewGuid().ToString())
            };

            foreach (var role in roles)
            {
                claims.Add(new Claim(ClaimTypes.Role, role));
            }

            var credentials = new SigningCredentials(_key, SecurityAlgorithms.HmacSha256);

            var token = new JwtSecurityToken(
                issuer: _configuration["JWT:Issuer"],
                audience: _configuration["JWT:Audience"],
                claims: claims,
                expires: DateTime.UtcNow.AddHours(24),
                signingCredentials: credentials
            );

            return new JwtSecurityTokenHandler().WriteToken(token);
        }

        public ClaimsPrincipal? ValidateToken(string token)
        {
            try
            {
                var tokenHandler = new JwtSecurityTokenHandler();
                var principal = tokenHandler.ValidateToken(token, new TokenValidationParameters
                {
                    ValidateIssuer = true,
                    ValidateAudience = true,
                    ValidateLifetime = true,
                    ValidateIssuerSigningKey = true,
                    ValidIssuer = _configuration["JWT:Issuer"],
                    ValidAudience = _configuration["JWT:Audience"],
                    IssuerSigningKey = _key
                }, out _);

                return principal;
            }
            catch
            {
                return null;
            }
        }
    }
}
```

**6.3 Create Authentication Endpoints**

Create `src/backend/[ProjectName].Api/Controllers/AuthController.cs`:

```csharp
using Microsoft.AspNetCore.Authorization;
using Microsoft.AspNetCore.Mvc;
using [ProjectName].Core.Interfaces;
using [ProjectName].Infrastructure.Services;

namespace [ProjectName].Api.Controllers
{
    [ApiController]
    [Route("api/[controller]")]
    public class AuthController : ControllerBase
    {
        private readonly IUserService _userService;
        private readonly IJwtService _jwtService;

        public AuthController(IUserService userService, IJwtService jwtService)
        {
            _userService = userService;
            _jwtService = jwtService;
        }

        [HttpPost("register")]
        [AllowAnonymous]
        public async Task<IActionResult> Register([FromBody] RegisterRequest request)
        {
            var user = await _userService.RegisterAsync(request.Email, request.Password, request.FirstName, request.LastName);
            return Ok(new { Message = "Registration successful" });
        }

        [HttpPost("login")]
        [AllowAnonymous]
        public async Task<IActionResult> Login([FromBody] LoginRequest request)
        {
            var user = await _userService.AuthenticateAsync(request.Email, request.Password);
            
            if (user == null)
                return Unauthorized(new { Message = "Invalid credentials" });

            var roles = await _userService.GetUserRolesAsync(user.Id);
            var token = _jwtService.GenerateToken(user.Id, user.Email, roles);

            return Ok(new { Token = token, User = user });
        }

        [HttpGet("me")]
        [Authorize]
        public async Task<IActionResult> GetCurrentUser()
        {
            var userId = int.Parse(User.FindFirst(ClaimTypes.NameIdentifier)?.Value ?? "0");
            var user = await _userService.GetByIdAsync(userId);
            return Ok(user);
        }
    }

    public record RegisterRequest(string Email, string Password, string FirstName, string LastName);
    public record LoginRequest(string Email, string Password);
}
```

**Output**: Working authentication system with JWT tokens

---

### Step 7: Configure Logging and Monitoring (1-2 hours)

#### Objective
Set up structured logging, monitoring, and observability.

#### Actions

**7.1 Configure Structured Logging**

For .NET, install Serilog:

```bash
dotnet add package Serilog.AspNetCore
dotnet add package Serilog.Sinks.Console
dotnet add package Serilog.Sinks.File
dotnet add package Serilog.Settings.Configuration
```

Update `Program.cs`:

```csharp
using Serilog;

var builder = WebApplication.CreateBuilder(args);

// Configure Serilog
Log.Logger = new LoggerConfiguration()
    .ReadFrom.Configuration(builder.Configuration)
    .Enrich.FromLogContext()
    .Enrich.WithProperty("Application", "YourAppName")
    .WriteTo.Console()
    .WriteTo.File("logs/app-.log", rollingInterval: RollingInterval.Day)
    .CreateLogger();

builder.Host.UseSerilog();

var app = builder.Build();

app.UseSerilogRequestLogging();

app.Run();
```

Add to `appsettings.json`:

```json
{
  "Serilog": {
    "MinimumLevel": {
      "Default": "Information",
      "Override": {
        "Microsoft": "Warning",
        "Microsoft.Hosting.Lifetime": "Information",
        "System": "Warning"
      }
    }
  }
}
```

**7.2 Add Health Checks**

Install health check packages:

```bash
dotnet add package Microsoft.Extensions.Diagnostics.HealthChecks
dotnet add package AspNetCore.HealthChecks.NpgSql
```

Configure in `Program.cs`:

```csharp
builder.Services.AddHealthChecks()
    .AddNpgSql(builder.Configuration.GetConnectionString("DefaultConnection"))
    .AddCheck("self", () => HealthCheckResult.Healthy());

app.MapHealthChecks("/health", new HealthCheckOptions
{
    ResponseWriter = UIResponseWriter.WriteHealthCheckUIResponse
});

app.MapHealthChecks("/health/ready", new HealthCheckOptions
{
    Predicate = check => check.Tags.Contains("ready"),
    ResponseWriter = UIResponseWriter.WriteHealthCheckUIResponse
});

app.MapHealthChecks("/health/live", new HealthCheckOptions
{
    Predicate = _ => false,
    ResponseWriter = UIResponseWriter.WriteHealthCheckUIResponse
});
```

**7.3 Add Application Insights (if using Azure)**

```bash
dotnet add package Microsoft.ApplicationInsights.AspNetCore
```

Configure in `Program.cs`:

```csharp
builder.Services.AddApplicationInsightsTelemetry(options =>
{
    options.ConnectionString = builder.Configuration["ApplicationInsights:ConnectionString"];
});
```

**Output**: Structured logging and health monitoring configured

---

### Step 8: Set Up Code Quality Standards (1 hour)

#### Objective
Establish and enforce code quality, linting, and formatting standards.

#### Actions

**8.1 Configure .NET Code Analysis**

Create `Directory.Build.props` in repository root:

```xml
<Project>
  <PropertyGroup>
    <AnalysisMode>All</AnalysisMode>
    <EnforceCodeStyleInBuild>true</EnforceCodeStyleInBuild>
    <TreatWarningsAsErrors>true</TreatWarningsAsErrors>
    <Nullable>enable</Nullable>
    <ImplicitUsings>enable</ImplicitUsings>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="StyleCop.Analyzers" Version="1.2.0-beta.435">
      <PrivateAssets>all</PrivateAssets>
      <IncludeAssets>runtime; build; native; contentfiles; analyzers; buildtransitive</IncludeAssets>
    </PackageReference>
  </ItemGroup>
</Project>
```

Create `.editorconfig` for C#:

```ini
# .NET Code Style Rules
[*.{cs,vb}]

# Organize usings
dotnet_sort_system_directives_first = true
dotnet_separate_import_directive_groups = false

# this. preferences
dotnet_style_qualification_for_field = false:warning
dotnet_style_qualification_for_property = false:warning
dotnet_style_qualification_for_method = false:warning
dotnet_style_qualification_for_event = false:warning

# Language keywords vs BCL types preferences
dotnet_style_predefined_type_for_locals_parameters_members = true:warning
dotnet_style_predefined_type_for_member_access = true:warning

# Parentheses preferences
dotnet_style_parentheses_in_arithmetic_binary_operators = always_for_clarity:silent
dotnet_style_parentheses_in_other_binary_operators = always_for_clarity:silent
dotnet_style_parentheses_in_relational_binary_operators = always_for_clarity:silent

# Modifier preferences
dotnet_style_require_accessibility_modifiers = always:warning
csharp_preferred_modifier_order = public,private,protected,internal,static,extern,new,virtual,abstract,sealed,override,readonly,unsafe,volatile,async:suggestion

# Expression-level preferences
dotnet_style_object_initializer = true:suggestion
dotnet_style_collection_initializer = true:suggestion
dotnet_style_prefer_auto_properties = true:suggestion
dotnet_style_explicit_tuple_names = true:suggestion

# Naming rules
dotnet_naming_rule.interfaces_should_be_prefixed_with_i.severity = warning
dotnet_naming_rule.interfaces_should_be_prefixed_with_i.symbols = interface
dotnet_naming_rule.interfaces_should_be_prefixed_with_i.style = begins_with_i

dotnet_naming_symbols.interface.applicable_kinds = interface
dotnet_naming_style.begins_with_i.required_prefix = I
dotnet_naming_style.begins_with_i.capitalization = pascal_case
```

**8.2 Configure Frontend Linting**

Install ESLint and Prettier:

```bash
cd src/frontend
npm install --save-dev eslint @typescript-eslint/parser @typescript-eslint/eslint-plugin
npm install --save-dev prettier eslint-config-prettier eslint-plugin-prettier
npm install --save-dev eslint-plugin-react eslint-plugin-react-hooks
```

Create `.eslintrc.json`:

```json
{
  "extends": [
    "eslint:recommended",
    "plugin:@typescript-eslint/recommended",
    "plugin:react/recommended",
    "plugin:react-hooks/recommended",
    "prettier"
  ],
  "parser": "@typescript-eslint/parser",
  "parserOptions": {
    "ecmaVersion": 2022,
    "sourceType": "module",
    "ecmaFeatures": {
      "jsx": true
    }
  },
  "plugins": ["@typescript-eslint", "react", "react-hooks"],
  "rules": {
    "@typescript-eslint/no-unused-vars": ["error", { "argsIgnorePattern": "^_" }],
    "@typescript-eslint/explicit-function-return-type": "off",
    "react/react-in-jsx-scope": "off",
    "react/prop-types": "off"
  },
  "settings": {
    "react": {
      "version": "detect"
    }
  }
}
```

Create `.prettierrc`:

```json
{
  "semi": true,
  "trailingComma": "es5",
  "singleQuote": true,
  "printWidth": 100,
  "tabWidth": 2,
  "useTabs": false
}
```

Add scripts to `package.json`:

```json
{
  "scripts": {
    "lint": "eslint . --ext .ts,.tsx",
    "lint:fix": "eslint . --ext .ts,.tsx --fix",
    "format": "prettier --write \"src/**/*.{ts,tsx,json,css,md}\"",
    "format:check": "prettier --check \"src/**/*.{ts,tsx,json,css,md}\""
  }
}
```

**8.3 Add Pre-commit Hooks**

Install Husky and lint-staged:

```bash
npm install --save-dev husky lint-staged
npx husky install
```

Add to `package.json`:

```json
{
  "lint-staged": {
    "*.{ts,tsx}": [
      "eslint --fix",
      "prettier --write"
    ],
    "*.{json,css,md}": [
      "prettier --write"
    ]
  }
}
```

Create `.husky/pre-commit`:

```bash
#!/bin/sh
. "$(dirname "$0")/_/husky.sh"

npx lint-staged
```

**Output**: Code quality standards enforced automatically

---

### Step 9: Configure Test Framework (1-2 hours)

#### Objective
Set up testing infrastructure with unit, integration, and E2E test support.

#### Actions

**9.1 Configure Backend Testing**

For .NET, the test project should already exist. Configure it:

Update `[ProjectName].Tests.csproj`:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>net8.0</TargetFramework>
    <Nullable>enable</Nullable>
    <IsPackable>false</IsPackable>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.NET.Test.Sdk" Version="17.8.0" />
    <PackageReference Include="xUnit" Version="2.6.2" />
    <PackageReference Include="xunit.runner.visualstudio" Version="2.5.4" />
    <PackageReference Include="coverlet.collector" Version="6.0.0" />
    <PackageReference Include="FluentAssertions" Version="6.12.0" />
    <PackageReference Include="Moq" Version="4.20.70" />
    <PackageReference Include="Microsoft.AspNetCore.Mvc.Testing" Version="8.0.0" />
    <PackageReference Include="Testcontainers" Version="3.6.0" />
  </ItemGroup>

  <ItemGroup>
    <ProjectReference Include="..\[ProjectName].Api\[ProjectName].Api.csproj" />
    <ProjectReference Include="..\[ProjectName].Core\[ProjectName].Core.csproj" />
    <ProjectReference Include="..\[ProjectName].Infrastructure\[ProjectName].Infrastructure.csproj" />
  </ItemGroup>

</Project>
```

Create example test:

```csharp
using FluentAssertions;
using Xunit;

namespace [ProjectName].Tests.Unit
{
    public class ExampleTests
    {
        [Fact]
        public void Example_Test_Should_Pass()
        {
            // Arrange
            var expected = 5;

            // Act
            var actual = 2 + 3;

            // Assert
            actual.Should().Be(expected);
        }
    }
}
```

**9.2 Configure Frontend Testing**

Install testing libraries:

```bash
cd src/frontend
npm install --save-dev vitest @testing-library/react @testing-library/jest-dom @testing-library/user-event jsdom
```

Create `vitest.config.ts`:

```typescript
import { defineConfig } from 'vitest/config';
import react from '@vitejs/plugin-react';

export default defineConfig({
  plugins: [react()],
  test: {
    globals: true,
    environment: 'jsdom',
    setupFiles: './src/test/setup.ts',
    coverage: {
      provider: 'v8',
      reporter: ['text', 'json', 'html', 'lcov'],
      exclude: [
        'node_modules/',
        'src/test/',
        '**/*.d.ts',
        '**/*.config.*',
        '**/mockData',
      ],
    },
  },
});
```

Create `src/test/setup.ts`:

```typescript
import '@testing-library/jest-dom';
import { expect, afterEach } from 'vitest';
import { cleanup } from '@testing-library/react';

// Cleanup after each test
afterEach(() => {
  cleanup();
});
```

Create example test `src/components/Button.test.tsx`:

```typescript
import { render, screen } from '@testing-library/react';
import { describe, it, expect } from 'vitest';
import Button from './Button';

describe('Button', () => {
  it('renders button with text', () => {
    render(<Button>Click me</Button>);
    expect(screen.getByRole('button', { name: /click me/i })).toBeInTheDocument();
  });

  it('calls onClick when clicked', async () => {
    const handleClick = vi.fn();
    render(<Button onClick={handleClick}>Click me</Button>);
    
    await userEvent.click(screen.getByRole('button'));
    expect(handleClick).toHaveBeenCalledOnce();
  });
});
```

Add test scripts to `package.json`:

```json
{
  "scripts": {
    "test": "vitest",
    "test:ui": "vitest --ui",
    "test:ci": "vitest run --coverage",
    "test:coverage": "vitest run --coverage"
  }
}
```

**9.3 Configure E2E Testing (Optional)**

Install Playwright:

```bash
npm install --save-dev @playwright/test
npx playwright install
```

Create `playwright.config.ts`:

```typescript
import { defineConfig, devices } from '@playwright/test';

export default defineConfig({
  testDir: './e2e',
  fullyParallel: true,
  forbidOnly: !!process.env.CI,
  retries: process.env.CI ? 2 : 0,
  workers: process.env.CI ? 1 : undefined,
  reporter: 'html',
  use: {
    baseURL: 'http://localhost:3000',
    trace: 'on-first-retry',
  },

  projects: [
    {
      name: 'chromium',
      use: { ...devices['Desktop Chrome'] },
    },
    {
      name: 'firefox',
      use: { ...devices['Desktop Firefox'] },
    },
    {
      name: 'webkit',
      use: { ...devices['Desktop Safari'] },
    },
  ],

  webServer: {
    command: 'npm run dev',
    url: 'http://localhost:3000',
    reuseExistingServer: !process.env.CI,
  },
});
```

**Output**: Complete test framework configured

---

### Step 10: Create Documentation Structure (30 minutes)

#### Objective
Establish documentation structure and create essential guides.

#### Actions

**10.1 Create Documentation Structure**

Create the following documentation files:

**docs/README.md**:
```markdown
# [Project Name] Documentation

## Table of Contents

- [Getting Started](./setup/getting-started.md)
- [Architecture](./architecture/README.md)
- [API Documentation](./api/README.md)
- [Development Guide](./setup/development-guide.md)
- [Testing Guide](./setup/testing-guide.md)
- [Deployment Guide](./setup/deployment-guide.md)
- [Contributing](./contributing.md)

## Quick Links

- [Project Board](link-to-board)
- [CI/CD Pipeline](link-to-pipeline)
- [Production Environment](link-to-prod)
- [Staging Environment](link-to-staging)
```

**docs/setup/getting-started.md**:
```markdown
# Getting Started

## Prerequisites

- Docker Desktop (version X.X or higher)
- Node.js (version 20.x)
- .NET SDK (version 8.0)
- Git

## Quick Start

1. Clone the repository:
   ```bash
   git clone [repo-url]
   cd [project-name]
   ```

2. Set up environment:
   ```bash
   ./scripts/setup-dev-env.sh
   ```

3. Access the application:
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:5000
   - API Documentation: http://localhost:5000/swagger

## Next Steps

- Read the [Development Guide](./development-guide.md)
- Review the [Architecture Documentation](../architecture/README.md)
- Check out [Contributing Guidelines](../contributing.md)
```

**docs/contributing.md**:
```markdown
# Contributing Guidelines

## Development Workflow

1. Create a feature branch from `develop`
2. Make your changes
3. Write tests
4. Ensure all tests pass
5. Run linting and formatting
6. Create a pull request
7. Address review comments
8. Merge after approval

## Branch Naming Convention

- `feature/` - New features
- `bugfix/` - Bug fixes
- `hotfix/` - Production hotfixes
- `refactor/` - Code refactoring
- `docs/` - Documentation updates

## Commit Message Convention

Follow [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>(<scope>): <description>

[optional body]

[optional footer]
```

Types: feat, fix, docs, style, refactor, test, chore

## Code Review Guidelines

- Be respectful and constructive
- Review for logic, not style (that's automated)
- Suggest improvements, don't demand changes
- Approve when ready, even if minor improvements suggested
```

**docs/architecture/README.md**:
```markdown
# Architecture Documentation

## Overview

[High-level description of the system architecture]

## Architecture Decision Records (ADRs)

- [ADR-001: Technology Stack Selection](./adr-001-technology-stack.md)
- [ADR-002: Authentication Strategy](./adr-002-authentication.md)
- [ADR-003: Database Choice](./adr-003-database.md)

## Component Diagram

[Insert C4 container diagram from architecture.md]

## Data Flow

[Describe how data flows through the system]

## Key Design Decisions

[List and explain key design decisions]
```

**Output**: Documentation structure with essential guides

---

### Step 11: Final Validation and Handoff (1 hour)

#### Objective
Validate that all infrastructure is working and prepare for team onboarding.

#### Actions

**11.1 Run Complete Validation**

Create `scripts/validate-setup.sh`:

```bash
#!/bin/bash

echo "Validating repository setup..."

# Check services are running
echo "Checking Docker services..."
docker-compose ps | grep -q "Up" || { echo "❌ Services not running"; exit 1; }
echo "✅ Docker services running"

# Check backend health
echo "Checking backend health..."
curl -f http://localhost:5000/health || { echo "❌ Backend health check failed"; exit 1; }
echo "✅ Backend healthy"

# Check frontend loads
echo "Checking frontend..."
curl -f http://localhost:3000 || { echo "❌ Frontend not accessible"; exit 1; }
echo "✅ Frontend accessible"

# Check database connectivity
echo "Checking database..."
docker-compose exec -T database psql -U devuser -d appdb -c "SELECT 1" || { echo "❌ Database connection failed"; exit 1; }
echo "✅ Database connected"

# Run backend tests
echo "Running backend tests..."
cd src/backend
dotnet test || { echo "❌ Backend tests failed"; exit 1; }
echo "✅ Backend tests passed"

# Run frontend tests
echo "Running frontend tests..."
cd ../frontend
npm run test:ci || { echo "❌ Frontend tests failed"; exit 1; }
echo "✅ Frontend tests passed"

# Check linting
echo "Checking code quality..."
npm run lint || { echo "❌ Linting failed"; exit 1; }
echo "✅ Code quality checks passed"

echo ""
echo "🎉 All validation checks passed!"
echo "Repository setup is complete and ready for team onboarding."
```

**11.2 Create Onboarding Checklist**

Create `docs/setup/onboarding-checklist.md`:

```markdown
# Developer Onboarding Checklist

## Access and Accounts

- [ ] Added to GitHub/GitLab organization
- [ ] Added to project board
- [ ] Added to CI/CD platform
- [ ] Added to cloud provider (if applicable)
- [ ] Added to team communication channels

## Local Setup

- [ ] Installed prerequisites (Docker, Node.js, .NET SDK)
- [ ] Cloned repository
- [ ] Ran setup script: `./scripts/setup-dev-env.sh`
- [ ] Verified all services running: `docker-compose ps`
- [ ] Accessed frontend: http://localhost:3000
- [ ] Accessed backend: http://localhost:5000
- [ ] Logged in with test credentials

## Validation

- [ ] Ran all tests: `./scripts/run-tests.sh`
- [ ] Ran linting: `npm run lint` and `dotnet format --verify-no-changes`
- [ ] Made a small change and created a PR
- [ ] Verified CI pipeline runs on PR

## Documentation Review

- [ ] Read [Getting Started Guide](./getting-started.md)
- [ ] Read [Development Guide](./development-guide.md)
- [ ] Read [Architecture Documentation](../architecture/README.md)
- [ ] Read [Contributing Guidelines](../contributing.md)

## Next Steps

- [ ] Attend architecture walkthrough session
- [ ] Review sprint backlog
- [ ] Pick up first task
- [ ] Pair with senior developer for first PR
```

**11.3 Create Handoff Document**

Create `artifacts/repository-setup-report.md`:

```markdown
# Repository Setup Report - [Project Name]

**Date**: [Date]
**Completed By**: DevOps Scaffolder Agent + Team

---

## Executive Summary

Repository infrastructure is complete and ready for feature development. All team members can now clone the repository, run the setup script, and begin contributing.

---

## What Was Completed

### ✅ Repository Structure
- Git repository initialized with proper structure
- Branch strategy configured (main, develop, feature/*, bugfix/*, etc.)
- Branch protection rules enabled
- Pull request template created

### ✅ CI/CD Pipeline
- Automated build pipeline configured
- Automated test execution
- Code coverage reporting
- Security scanning
- Automated deployment to dev/staging/prod
- Pipeline runs on every PR and merge

### ✅ Local Development Environment
- Docker-based local development setup
- One-command environment setup: `./scripts/setup-dev-env.sh`
- Hot-reload for frontend and backend
- Database with seed data
- Email testing with Mailhog
- All services containerized

### ✅ Database
- PostgreSQL configured (or SQL Server, MongoDB, etc.)
- Entity Framework migrations set up
- Initial schema created
- Seed data for development
- Migration scripts automated

### ✅ Authentication
- JWT-based authentication implemented
- Login and registration endpoints
- Role-based authorization
- Token validation middleware
- Secure password hashing

### ✅ Logging and Monitoring
- Structured logging with Serilog
- Health check endpoints
- Application Insights configured (if applicable)
- Log aggregation ready

### ✅ Code Quality
- Linting configured (ESLint, StyleCop)
- Code formatting (Prettier, EditorConfig)
- Pre-commit hooks
- Code analysis in CI pipeline
- 80% coverage requirement enforced

### ✅ Testing Infrastructure
- Unit test framework (xUnit, Vitest)
- Integration test support
- E2E test framework (Playwright)
- Code coverage reporting
- Test execution in CI

### ✅ Documentation
- README with getting started guide
- Architecture documentation
- API documentation structure
- Contributing guidelines
- Developer onboarding checklist

---

## Access Information

**Repository**: [URL]
**CI/CD Pipeline**: [URL]
**Dev Environment**: [URL]
**Staging Environment**: [URL]
**Production Environment**: [URL]

**Container Registry**: [URL]
**Project Board**: [URL]

---

## Validation Results

All validation checks passed:
- ✅ Docker services running
- ✅ Backend health check passing
- ✅ Frontend accessible
- ✅ Database connected
- ✅ All tests passing
- ✅ Linting passing
- ✅ CI pipeline successful

---

## Team Onboarding

Team members can onboard by following:
1. Access and accounts setup (listed in onboarding checklist)
2. Run `./scripts/setup-dev-env.sh`
3. Verify setup with `./scripts/validate-setup.sh`
4. Review documentation in `docs/`
5. Pick up first task from sprint backlog

---

## Next Steps

Ready for Phase 3 (Implementation):
- ✅ Development infrastructure complete
- ✅ Team can begin Sprint 0
- ✅ Feature development can commence

---

## Support and Troubleshooting

For issues:
1. Check troubleshooting section in docs
2. Ask in team chat channel
3. Review CI/CD logs
4. Contact DevOps lead

**This repository setup is complete and validated. The team is ready to begin feature development.**
```

**Output**: Validated infrastructure and comprehensive handoff documentation

---

## Success Criteria

This repository setup workflow is complete when:

✅ **Repository initialized**: Proper structure and branch strategy established  
✅ **CI/CD configured**: Automated build, test, and deploy pipeline working  
✅ **Local dev environment**: One-command setup that works for all team members  
✅ **Database ready**: Schema, migrations, and seed data configured  
✅ **Authentication implemented**: JWT-based auth with login/register endpoints  
✅ **Logging configured**: Structured logging and health checks in place  
✅ **Code quality enforced**: Linting, formatting, and pre-commit hooks active  
✅ **Testing framework**: Unit, integration, and E2E tests ready  
✅ **Documentation complete**: All essential guides and checklists created  
✅ **Validation passed**: All services running and tests passing  
✅ **Team can onboard**: Clear onboarding process documented

---

## Handoff to Sprint 0 Execution

With repository setup complete, Sprint 0 can begin:

**What Sprint 0 Execution Needs**:
1. ✅ Working development environment
2. ✅ CI/CD pipeline functional
3. ✅ Team members onboarded
4. ✅ First task assignments from sprint plan

**Next Phase**: Phase 3 - Implementation (Sprint 0 execution begins)

**The team can now**:
- Clone repository
- Run setup script
- Begin implementing features from sprint backlog
- Collaborate with confidence in infrastructure

---

## Troubleshooting

### Issue: Docker services won't start

**Symptom**: `docker-compose up` fails

**Solutions**:
- Check Docker Desktop is running
- Verify ports 3000, 5000, 5432 are not in use
- Check disk space available
- Try `docker-compose down -v` then `docker-compose up --build`

---

### Issue: Database migrations fail

**Symptom**: Migration commands error out

**Solutions**:
- Verify database service is running: `docker-compose ps`
- Check database logs: `docker-compose logs database`
- Ensure connection string is correct in .env
- Try: `docker-compose restart database`

---

### Issue: CI pipeline fails but works locally

**Symptom**: Tests pass locally but fail in CI

**Solutions**:
- Check environment variables are set in CI
- Verify secrets are configured
- Check build logs for missing dependencies
- Ensure database/services are available in CI

---

### Issue: Team member can't access cloud resources

**Symptom**: Permission errors when trying to deploy

**Solutions**:
- Verify user added to cloud provider organization
- Check role assignments (Contributor, etc.)
- Verify service principal permissions
- Check network access rules

---

**This workflow provides a systematic approach to establishing complete development infrastructure. Follow it step-by-step to create a production-ready repository that enables efficient team collaboration and rapid feature development.**
