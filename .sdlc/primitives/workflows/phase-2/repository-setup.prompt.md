# Repository Setup Workflow

## Purpose

This workflow guides you through the systematic process of creating a **production-ready development infrastructure** from architecture and requirements. The output is a complete repository with working CI/CD, containerization, and development environment that developers can clone and immediately use.

**What This Workflow Accomplishes**:
- Discovers and validates technology stack choices
- Creates standardized repository structure
- Sets up Docker containerization for all services
- Configures CI/CD pipeline with quality gates
- Creates development environment setup automation
- Generates comprehensive developer documentation
- Validates infrastructure is functional and ready

**What This Workflow Does NOT Do**:
- Make architecture decisions (that's Phase 1)
- Write application code (that's Phase 3)
- Choose technologies arbitrarily (follows architecture.md)
- Skip quality standards (follows constitution.md)

---

## Prerequisites

### Required Inputs

Before starting, ensure you have:

- [ ] **Constitution** (`constitution.md`) - Quality standards, coding conventions, constraints
- [ ] **Architecture Document** (`architecture.md`) - Technology stack, component structure, patterns
- [ ] **Data Model** (`data-model.md`) - Database schema and relationships
- [ ] **API Specification** (`api-spec.json`) - API contracts and endpoints
- [ ] **Quality Strategy** (`quality-strategy.md`) - Testing requirements, coverage targets
- [ ] **Sprint Plan** (`sprint-plan.md`) - Timeline context for Sprint 0 infrastructure work
- [ ] **Team Context** (`team-context.md`) - Developer skill levels and preferences

### Agent Setup

You should be in **DevOps Scaffolder** mode with all context loaded:

```markdown
You are the DevOps Scaffolder Agent, an expert in infrastructure setup, 
containerization, CI/CD pipelines, and development tooling.

Context loaded:
- Constitution.md (quality standards)
- Architecture.md (technology choices)
- Data-model.md (database requirements)
- API-spec.json (service contracts)
- Quality-strategy.md (testing requirements)
- Sprint-plan.md (timeline context)
- Team-context.md (developer needs)

Your mission: Create a production-ready development infrastructure that 
developers can clone and immediately start coding in.

Ready to begin repository setup.
```

### Session Setup

Create a focused infrastructure session:

```bash
# Create working directory for repository setup
mkdir -p .phase2/sessions/[project-name]/infrastructure

# Navigate to working directory
cd .phase2/sessions/[project-name]/infrastructure

# This is where you'll build the repository structure
```

---

## Overview: The Repository Setup Process

```
Architecture + Requirements
           ↓
    [Step 0: Technology Discovery]
           ↓
Technology Stack Confirmed
           ↓
    [Step 1: Repository Structure]
           ↓
Folder Structure Created
           ↓
    [Step 2: Containerization]
           ↓
Docker Configuration Complete
           ↓
    [Step 3: CI/CD Pipeline]
           ↓
Automated Pipeline Configured
           ↓
    [Step 4: Development Environment]
           ↓
Developer Setup Automated
           ↓
    [Step 5: Documentation]
           ↓
Developer Docs Complete
           ↓
    [Step 6: Validation]
           ↓
Infrastructure Ready for Phase 3
```

**Estimated Time**: 2-3 days (depending on stack complexity)

---

## Step 0: Technology Stack Discovery (1-2 hours)

### Objective

**CRITICAL**: Discover and validate all technology choices before generating any infrastructure. Never assume - always confirm.

### Actions

#### 0.1 Review Architecture Document

Extract technology decisions from `architecture.md`:

```markdown
## Technology Stack Discovery Checklist

**Programming Languages**:
- [ ] Backend language(s): [e.g., C#, Python, Node.js]
- [ ] Backend version: [e.g., .NET 8, Python 3.12, Node 20]
- [ ] Frontend framework: [e.g., React, Vue, Angular, Blazor]
- [ ] Frontend version: [e.g., React 18]

**Frameworks & Libraries**:
- [ ] Backend framework: [e.g., ASP.NET Core, FastAPI, Express]
- [ ] ORM/Data access: [e.g., Entity Framework, Dapper, SQLAlchemy]
- [ ] Testing frameworks: [e.g., xUnit, Playwright, Jest]
- [ ] UI library: [e.g., MUI, Tailwind, Bootstrap]

**Databases**:
- [ ] Primary database: [e.g., PostgreSQL, SQL Server, MongoDB]
- [ ] Database version: [e.g., PostgreSQL 16]
- [ ] Caching layer: [e.g., Redis, Memcached, none]
- [ ] Search engine: [e.g., Elasticsearch, none]

**Infrastructure**:
- [ ] Container runtime: [e.g., Docker]
- [ ] Orchestration: [e.g., Docker Compose, Kubernetes, none for dev]
- [ ] Cloud provider: [e.g., Azure, AWS, GCP, on-prem]
- [ ] Web server: [e.g., Kestrel, nginx, IIS]

**CI/CD**:
- [ ] CI/CD platform: [e.g., GitHub Actions, Azure DevOps, GitLab CI]
- [ ] Build system: [e.g., dotnet CLI, npm, Maven]
- [ ] Package manager: [e.g., NuGet, npm, pip]

**Development Tools**:
- [ ] IDE: [e.g., Visual Studio, VS Code, Rider]
- [ ] Code formatter: [e.g., dotnet format, Prettier, Black]
- [ ] Linter: [e.g., Roslyn analyzers, ESLint, Pylint]
- [ ] API testing: [e.g., Postman, REST Client, Swagger]

**Quality & Security**:
- [ ] Code coverage: [e.g., Coverlet, Jest coverage]
- [ ] Security scanning: [e.g., Dependabot, Snyk, OWASP ZAP]
- [ ] Code quality: [e.g., SonarQube, CodeQL]
- [ ] Performance testing: [e.g., k6, JMeter, custom]
```

#### 0.2 Identify Gaps and Assumptions

If architecture.md is incomplete, ask stakeholders:

```markdown
## Technology Stack Questions

**Missing Critical Decisions**:
1. [Question about missing technology choice]
   - Options: [A, B, C]
   - Recommendation: [X] because [rationale]
   - Impact if not decided: [description]

2. [Question about missing technology choice]
   - Options: [A, B, C]
   - Recommendation: [X] because [rationale]
   - Impact if not decided: [description]

**Confirmation Needed**:
- Backend will be C# with ASP.NET Core - correct?
- Frontend will be React with TypeScript - correct?
- PostgreSQL for database - correct?
- GitHub Actions for CI/CD - correct?
```

**DO NOT PROCEED** until all technology choices are confirmed.

#### 0.3 Validate Technology Compatibility

Check that chosen technologies work together:

```markdown
## Compatibility Validation

**Stack Combination**: C# + ASP.NET Core + React + PostgreSQL + Docker

**Compatibility Checks**:
- [ ] Framework versions compatible (e.g., .NET 8 supports Linux containers)
- [ ] Database drivers available (e.g., Npgsql for PostgreSQL + .NET)
- [ ] Build tools work together (e.g., npm + dotnet in same pipeline)
- [ ] Docker images available (e.g., mcr.microsoft.com/dotnet/sdk:8.0)
- [ ] IDE support exists (e.g., VS Code C# extension + React extensions)

**Known Issues**:
- [List any known compatibility issues or workarounds needed]

**Workarounds Required**:
- [Describe any special configuration needed]
```

#### 0.4 Create Technology Stack Document

Document final confirmed stack:

```markdown
# Technology Stack - [Project Name]

**Date**: [YYYY-MM-DD]  
**Version**: 1.0  
**Status**: Confirmed

## Backend Stack

**Language**: C# 12  
**Runtime**: .NET 8.0  
**Framework**: ASP.NET Core 8.0 (Web API)  
**ORM**: Entity Framework Core 8.0  
**Testing**: xUnit 2.6 + Moq 4.20  
**API Documentation**: Swagger/OpenAPI 3.0

## Frontend Stack

**Language**: TypeScript 5.3  
**Framework**: React 18.2  
**Build Tool**: Vite 5.0  
**UI Library**: Material-UI (MUI) 5.14  
**Testing**: Vitest + React Testing Library  
**E2E Testing**: Playwright 1.40

## Database Stack

**Database**: PostgreSQL 16  
**Migrations**: Entity Framework Core Migrations  
**Caching**: Redis 7.2 (optional, for production)  
**Database Tooling**: pgAdmin 4

## Infrastructure

**Containerization**: Docker 24.0  
**Orchestration**: Docker Compose 2.23  
**Web Server**: Kestrel (ASP.NET Core built-in)  
**Reverse Proxy**: nginx 1.25 (production only)

## CI/CD

**Platform**: GitHub Actions  
**Build**: dotnet CLI 8.0 + npm 10.2  
**Testing**: Automated test execution in pipeline  
**Quality Gates**: Code coverage (>80%), linting, security scan  
**Deployment**: Docker image build and push

## Development Tools

**IDE**: Visual Studio Code (recommended) or Visual Studio 2022  
**Extensions**:
- C# Dev Kit
- ESLint
- Prettier
- Docker
- GitLens

**Code Quality**:
- Formatter: dotnet format + Prettier
- Linter: Roslyn analyzers + ESLint
- Code Coverage: Coverlet
- Security: Dependabot + GitHub Advanced Security

## Version Requirements

- Docker: ≥ 24.0
- Docker Compose: ≥ 2.20
- Node.js: ≥ 20.0 (LTS)
- .NET SDK: ≥ 8.0
- PostgreSQL: ≥ 15.0
```

**Output**: `technology-stack.md` (confirmed and approved)

---

## Step 1: Repository Structure Creation (3-4 hours)

### Objective

Create a logical, maintainable repository structure that follows architecture and best practices.

### Actions

#### 1.1 Determine Repository Strategy

Choose between monorepo or multi-repo:

```markdown
## Repository Strategy Decision

**Option 1: Monorepo** (Single repository for all code)
- **Pros**: Easier coordination, shared tooling, atomic commits
- **Cons**: Larger repo, potential build complexity
- **Best For**: Small-medium teams, tightly coupled services

**Option 2: Multi-repo** (Separate repos per service)
- **Pros**: Independent deployment, clear boundaries, smaller repos
- **Cons**: Coordination overhead, duplicate tooling, versioning complexity
- **Best For**: Large teams, microservices, independent services

**Decision**: [Monorepo / Multi-repo]  
**Rationale**: [Why this choice fits the project]

**If Monorepo**: Create single repository with all components  
**If Multi-repo**: Follow this workflow for each repository separately
```

#### 1.2 Design Repository Structure

Based on architecture and technology stack, design folder structure:

**Example: C# Backend + React Frontend Monorepo**

```
project-root/
├── .github/                    # GitHub-specific files
│   ├── workflows/              # CI/CD pipeline definitions
│   │   ├── ci.yml              # Continuous integration
│   │   ├── cd.yml              # Continuous deployment
│   │   └── security.yml        # Security scanning
│   ├── ISSUE_TEMPLATE/         # Issue templates
│   └── PULL_REQUEST_TEMPLATE.md
├── docs/                       # Documentation
│   ├── architecture/           # Architecture docs (from Phase 1)
│   ├── api/                    # API documentation
│   ├── development/            # Developer guides
│   └── deployment/             # Deployment guides
├── src/                        # Source code
│   ├── backend/                # Backend services
│   │   ├── Api/                # Web API project
│   │   │   ├── Controllers/    # API controllers
│   │   │   ├── Models/         # DTOs and request/response models
│   │   │   ├── Services/       # Business logic services
│   │   │   ├── Program.cs      # Application entry point
│   │   │   └── Api.csproj      # Project file
│   │   ├── Core/               # Core domain logic
│   │   │   ├── Entities/       # Domain entities
│   │   │   ├── Interfaces/     # Abstractions
│   │   │   └── Core.csproj
│   │   ├── Infrastructure/     # Infrastructure concerns
│   │   │   ├── Data/           # Database context and repositories
│   │   │   ├── Services/       # External service integrations
│   │   │   └── Infrastructure.csproj
│   │   └── Backend.sln         # Solution file
│   └── frontend/               # Frontend application
│       ├── public/             # Static assets
│       ├── src/
│       │   ├── components/     # React components
│       │   ├── pages/          # Page components
│       │   ├── services/       # API service layer
│       │   ├── hooks/          # Custom React hooks
│       │   ├── utils/          # Utility functions
│       │   ├── App.tsx         # Root component
│       │   └── main.tsx        # Entry point
│       ├── package.json
│       ├── vite.config.ts
│       └── tsconfig.json
├── tests/                      # Test projects
│   ├── Api.Tests/              # API unit tests
│   ├── Core.Tests/             # Core logic tests
│   ├── Integration.Tests/      # Integration tests
│   └── E2E.Tests/              # End-to-end tests (Playwright)
├── scripts/                    # Utility scripts
│   ├── setup-dev.sh            # Development setup script
│   ├── migrate-db.sh           # Database migration script
│   └── seed-data.sh            # Test data seeding
├── infrastructure/             # Infrastructure as code
│   ├── docker/                 # Docker-related files
│   │   ├── backend.Dockerfile
│   │   ├── frontend.Dockerfile
│   │   └── nginx.conf
│   ├── k8s/                    # Kubernetes manifests (if applicable)
│   └── terraform/              # Terraform configs (if applicable)
├── .dockerignore               # Docker ignore file
├── .editorconfig               # Editor configuration
├── .gitignore                  # Git ignore rules
├── docker-compose.yml          # Local development orchestration
├── docker-compose.override.yml # Local overrides
├── README.md                   # Project README
├── CONTRIBUTING.md             # Contribution guidelines
├── LICENSE                     # License file
└── .env.example                # Environment variable template
```

#### 1.3 Create Directory Structure

Generate the complete folder structure:

```bash
# Create main directories
mkdir -p .github/workflows
mkdir -p .github/ISSUE_TEMPLATE
mkdir -p docs/{architecture,api,development,deployment}
mkdir -p src/backend/{Api,Core,Infrastructure}
mkdir -p src/frontend/{public,src}
mkdir -p tests/{Api.Tests,Core.Tests,Integration.Tests,E2E.Tests}
mkdir -p scripts
mkdir -p infrastructure/{docker,k8s,terraform}

# Create subdirectories based on architecture
mkdir -p src/backend/Api/{Controllers,Models,Services}
mkdir -p src/backend/Core/{Entities,Interfaces}
mkdir -p src/backend/Infrastructure/{Data,Services}
mkdir -p src/frontend/src/{components,pages,services,hooks,utils}

# Create placeholder README files
echo "# Backend API" > src/backend/Api/README.md
echo "# Core Domain" > src/backend/Core/README.md
echo "# Infrastructure" > src/backend/Infrastructure/README.md
echo "# Frontend Application" > src/frontend/README.md
echo "# Tests" > tests/README.md
```

#### 1.4 Create Core Configuration Files

Generate essential configuration files:

**`.gitignore`**:

```gitignore
# Build outputs
[Bb]in/
[Oo]bj/
[Dd]ist/
[Bb]uild/
*.dll
*.exe
*.pdb

# User-specific files
*.suo
*.user
*.userosscache
*.sln.docstates
.vs/
.vscode/

# Node modules and dependencies
node_modules/
npm-debug.log*
yarn-debug.log*
yarn-error.log*
package-lock.json
yarn.lock

# Environment files
.env
.env.local
.env.*.local
*.env

# Database files
*.db
*.db-shm
*.db-wal

# OS files
.DS_Store
Thumbs.db

# IDE files
.idea/
*.swp
*.swo
*~

# Test coverage
coverage/
*.coverage
.coveralls.yml

# Docker volumes
docker-compose.override.yml
```

**`.editorconfig`**:

```ini
root = true

[*]
charset = utf-8
end_of_line = lf
insert_final_newline = true
trim_trailing_whitespace = true

[*.{cs,csx}]
indent_style = space
indent_size = 4

[*.{js,jsx,ts,tsx,json}]
indent_style = space
indent_size = 2

[*.{yml,yaml}]
indent_style = space
indent_size = 2

[*.md]
trim_trailing_whitespace = false
```

**`.env.example`**:

```bash
# Database Configuration
DATABASE_HOST=localhost
DATABASE_PORT=5432
DATABASE_NAME=projectdb
DATABASE_USER=postgres
DATABASE_PASSWORD=yourpassword

# Application Configuration
ASPNETCORE_ENVIRONMENT=Development
ASPNETCORE_URLS=http://+:5000
API_BASE_URL=http://localhost:5000

# Frontend Configuration
VITE_API_URL=http://localhost:5000/api
VITE_APP_NAME=ProjectName

# Redis Configuration (optional)
REDIS_HOST=localhost
REDIS_PORT=6379

# JWT Configuration
JWT_SECRET_KEY=your-secret-key-change-in-production
JWT_EXPIRATION_HOURS=24
```

#### 1.5 Create Project Files

Generate language-specific project files:

**Backend: `src/backend/Backend.sln`**:

```bash
dotnet new sln -n Backend -o src/backend
dotnet new webapi -n Api -o src/backend/Api
dotnet new classlib -n Core -o src/backend/Core
dotnet new classlib -n Infrastructure -o src/backend/Infrastructure

# Add projects to solution
cd src/backend
dotnet sln add Api/Api.csproj
dotnet sln add Core/Core.csproj
dotnet sln add Infrastructure/Infrastructure.csproj

# Add project references
cd Api
dotnet add reference ../Core/Core.csproj
dotnet add reference ../Infrastructure/Infrastructure.csproj

cd ../Infrastructure
dotnet add reference ../Core/Core.csproj
```

**Frontend: `src/frontend/package.json`**:

```json
{
  "name": "project-frontend",
  "private": true,
  "version": "0.1.0",
  "type": "module",
  "scripts": {
    "dev": "vite",
    "build": "tsc && vite build",
    "preview": "vite preview",
    "lint": "eslint . --ext ts,tsx --report-unused-disable-directives --max-warnings 0",
    "format": "prettier --write \"src/**/*.{ts,tsx,css}\"",
    "test": "vitest",
    "test:ui": "vitest --ui",
    "test:coverage": "vitest --coverage"
  },
  "dependencies": {
    "react": "^18.2.0",
    "react-dom": "^18.2.0",
    "react-router-dom": "^6.20.0",
    "@mui/material": "^5.14.0",
    "@mui/icons-material": "^5.14.0",
    "axios": "^1.6.0"
  },
  "devDependencies": {
    "@types/react": "^18.2.0",
    "@types/react-dom": "^18.2.0",
    "@typescript-eslint/eslint-plugin": "^6.0.0",
    "@typescript-eslint/parser": "^6.0.0",
    "@vitejs/plugin-react": "^4.2.0",
    "eslint": "^8.55.0",
    "eslint-plugin-react-hooks": "^4.6.0",
    "eslint-plugin-react-refresh": "^0.4.0",
    "prettier": "^3.1.0",
    "typescript": "^5.3.0",
    "vite": "^5.0.0",
    "vitest": "^1.0.0",
    "@vitest/ui": "^1.0.0",
    "@testing-library/react": "^14.0.0",
    "@testing-library/jest-dom": "^6.0.0"
  }
}
```

**Frontend: `src/frontend/vite.config.ts`**:

```typescript
import { defineConfig } from 'vite';
import react from '@vitejs/plugin-react';

export default defineConfig({
  plugins: [react()],
  server: {
    port: 3000,
    proxy: {
      '/api': {
        target: 'http://localhost:5000',
        changeOrigin: true,
      },
    },
  },
  build: {
    outDir: 'dist',
    sourcemap: true,
  },
});
```

**Frontend: `src/frontend/tsconfig.json`**:

```json
{
  "compilerOptions": {
    "target": "ES2020",
    "useDefineForClassFields": true,
    "lib": ["ES2020", "DOM", "DOM.Iterable"],
    "module": "ESNext",
    "skipLibCheck": true,
    "moduleResolution": "bundler",
    "allowImportingTsExtensions": true,
    "resolveJsonModule": true,
    "isolatedModules": true,
    "noEmit": true,
    "jsx": "react-jsx",
    "strict": true,
    "noUnusedLocals": true,
    "noUnusedParameters": true,
    "noFallthroughCasesInSwitch": true
  },
  "include": ["src"],
  "references": [{ "path": "./tsconfig.node.json" }]
}
```

**Output**: Complete repository structure with all configuration files

---

## Step 2: Containerization Setup (4-6 hours)

### Objective

Create Docker configurations for all services to enable consistent development and deployment environments.

### Actions

#### 2.1 Create Backend Dockerfile

**`infrastructure/docker/backend.Dockerfile`**:

```dockerfile
# Build stage
FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR /src

# Copy solution and project files
COPY src/backend/*.sln .
COPY src/backend/Api/*.csproj ./Api/
COPY src/backend/Core/*.csproj ./Core/
COPY src/backend/Infrastructure/*.csproj ./Infrastructure/

# Restore dependencies
RUN dotnet restore

# Copy source code
COPY src/backend/Api/. ./Api/
COPY src/backend/Core/. ./Core/
COPY src/backend/Infrastructure/. ./Infrastructure/

# Build and publish
WORKDIR /src/Api
RUN dotnet publish -c Release -o /app/publish

# Runtime stage
FROM mcr.microsoft.com/dotnet/aspnet:8.0 AS runtime
WORKDIR /app

# Install curl for health checks
RUN apt-get update && apt-get install -y curl && rm -rf /var/lib/apt/lists/*

# Copy published app
COPY --from=build /app/publish .

# Create non-root user
RUN useradd -m -u 1000 appuser && chown -R appuser:appuser /app
USER appuser

# Expose port
EXPOSE 5000

# Health check
HEALTHCHECK --interval=30s --timeout=3s --start-period=5s --retries=3 \
  CMD curl -f http://localhost:5000/health || exit 1

# Entry point
ENTRYPOINT ["dotnet", "Api.dll"]
```

#### 2.2 Create Frontend Dockerfile

**`infrastructure/docker/frontend.Dockerfile`**:

```dockerfile
# Build stage
FROM node:20-alpine AS build
WORKDIR /app

# Copy package files
COPY src/frontend/package*.json ./

# Install dependencies
RUN npm ci

# Copy source code
COPY src/frontend/. .

# Build application
RUN npm run build

# Runtime stage with nginx
FROM nginx:1.25-alpine AS runtime
WORKDIR /usr/share/nginx/html

# Remove default nginx static files
RUN rm -rf ./*

# Copy built app
COPY --from=build /app/dist .

# Copy nginx configuration
COPY infrastructure/docker/nginx.conf /etc/nginx/nginx.conf

# Create non-root user
RUN chown -R nginx:nginx /usr/share/nginx/html && \
    chown -R nginx:nginx /var/cache/nginx && \
    chown -R nginx:nginx /var/log/nginx && \
    chown -R nginx:nginx /etc/nginx/conf.d

# Use non-root user
USER nginx

# Expose port
EXPOSE 80

# Health check
HEALTHCHECK --interval=30s --timeout=3s --start-period=5s --retries=3 \
  CMD wget --quiet --tries=1 --spider http://localhost/health || exit 1

# Start nginx
CMD ["nginx", "-g", "daemon off;"]
```

#### 2.3 Create nginx Configuration

**`infrastructure/docker/nginx.conf`**:

```nginx
events {
    worker_connections 1024;
}

http {
    include /etc/nginx/mime.types;
    default_type application/octet-stream;

    # Logging
    access_log /var/log/nginx/access.log;
    error_log /var/log/nginx/error.log;

    # Performance
    sendfile on;
    tcp_nopush on;
    tcp_nodelay on;
    keepalive_timeout 65;
    types_hash_max_size 2048;

    # Gzip compression
    gzip on;
    gzip_vary on;
    gzip_types text/plain text/css text/xml text/javascript 
               application/x-javascript application/xml+rss 
               application/json application/javascript;

    server {
        listen 80;
        server_name _;
        root /usr/share/nginx/html;
        index index.html;

        # Health check endpoint
        location /health {
            access_log off;
            return 200 "healthy\n";
            add_header Content-Type text/plain;
        }

        # API proxy
        location /api/ {
            proxy_pass http://backend:5000/api/;
            proxy_http_version 1.1;
            proxy_set_header Upgrade $http_upgrade;
            proxy_set_header Connection 'upgrade';
            proxy_set_header Host $host;
            proxy_set_header X-Real-IP $remote_addr;
            proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
            proxy_set_header X-Forwarded-Proto $scheme;
            proxy_cache_bypass $http_upgrade;
        }

        # React app - try files first, fallback to index.html for client-side routing
        location / {
            try_files $uri $uri/ /index.html;
        }

        # Cache static assets
        location ~* \.(js|css|png|jpg|jpeg|gif|ico|svg|woff|woff2|ttf|eot)$ {
            expires 1y;
            add_header Cache-Control "public, immutable";
        }
    }
}
```

#### 2.4 Create Docker Compose for Development

**`docker-compose.yml`**:

```yaml
version: '3.8'

services:
  # PostgreSQL Database
  database:
    image: postgres:16-alpine
    container_name: projectname-db
    environment:
      POSTGRES_DB: ${DATABASE_NAME:-projectdb}
      POSTGRES_USER: ${DATABASE_USER:-postgres}
      POSTGRES_PASSWORD: ${DATABASE_PASSWORD:-postgres}
    ports:
      - "5432:5432"
    volumes:
      - postgres-data:/var/lib/postgresql/data
      - ./scripts/init-db.sql:/docker-entrypoint-initdb.d/init.sql
    healthcheck:
      test: ["CMD-SHELL", "pg_isready -U postgres"]
      interval: 10s
      timeout: 5s
      retries: 5
    networks:
      - app-network

  # Redis Cache (optional)
  cache:
    image: redis:7.2-alpine
    container_name: projectname-cache
    ports:
      - "6379:6379"
    volumes:
      - redis-data:/data
    healthcheck:
      test: ["CMD", "redis-cli", "ping"]
      interval: 10s
      timeout: 3s
      retries: 5
    networks:
      - app-network

  # Backend API
  backend:
    build:
      context: .
      dockerfile: infrastructure/docker/backend.Dockerfile
    container_name: projectname-api
    environment:
      ASPNETCORE_ENVIRONMENT: Development
      ASPNETCORE_URLS: http://+:5000
      ConnectionStrings__DefaultConnection: "Host=database;Port=5432;Database=${DATABASE_NAME:-projectdb};Username=${DATABASE_USER:-postgres};Password=${DATABASE_PASSWORD:-postgres}"
      Redis__Host: cache
      Redis__Port: 6379
    ports:
      - "5000:5000"
    depends_on:
      database:
        condition: service_healthy
      cache:
        condition: service_healthy
    volumes:
      - ./src/backend:/src/backend:ro
      - backend-nuget:/root/.nuget/packages
    networks:
      - app-network
    restart: unless-stopped

  # Frontend Application
  frontend:
    build:
      context: .
      dockerfile: infrastructure/docker/frontend.Dockerfile
    container_name: projectname-frontend
    environment:
      VITE_API_URL: http://localhost:5000/api
    ports:
      - "3000:80"
    depends_on:
      - backend
    networks:
      - app-network
    restart: unless-stopped

  # pgAdmin (optional - database management)
  pgadmin:
    image: dpage/pgadmin4:latest
    container_name: projectname-pgadmin
    environment:
      PGADMIN_DEFAULT_EMAIL: admin@example.com
      PGADMIN_DEFAULT_PASSWORD: admin
      PGADMIN_CONFIG_SERVER_MODE: 'False'
    ports:
      - "5050:80"
    volumes:
      - pgadmin-data:/var/lib/pgadmin
    depends_on:
      - database
    networks:
      - app-network
    profiles:
      - tools

volumes:
  postgres-data:
    driver: local
  redis-data:
    driver: local
  pgadmin-data:
    driver: local
  backend-nuget:
    driver: local

networks:
  app-network:
    driver: bridge
```

#### 2.5 Create Docker Compose Override for Development

**`docker-compose.override.yml`** (gitignored for local customization):

```yaml
version: '3.8'

services:
  backend:
    environment:
      ASPNETCORE_ENVIRONMENT: Development
      Logging__LogLevel__Default: Debug
    volumes:
      # Enable hot reload (if supported)
      - ./src/backend:/src/backend
    command: dotnet watch run --project /src/backend/Api/Api.csproj

  frontend:
    volumes:
      # Enable hot reload
      - ./src/frontend:/app
      - /app/node_modules
    command: npm run dev -- --host 0.0.0.0

  database:
    environment:
      # Additional dev settings
      POSTGRES_HOST_AUTH_METHOD: trust
```

#### 2.6 Create .dockerignore

**`.dockerignore`**:

```
# Build artifacts
**/bin/
**/obj/
**/dist/
**/build/
**/.next/
**/out/

# Dependencies
**/node_modules/
**/.nuget/

# Environment files
**/.env
**/.env.local

# IDE
**/.vs/
**/.vscode/
**/.idea/

# Git
**/.git/
**/.gitignore

# Documentation
**/docs/
**/README.md

# Tests
**/tests/
**/*.Tests/

# OS files
**/.DS_Store
**/Thumbs.db
```

**Output**: Complete Docker setup with development and production configurations

---

## Step 3: CI/CD Pipeline Configuration (4-6 hours)

### Objective

Create automated CI/CD pipeline with quality gates that enforces constitution standards.

### Actions

#### 3.1 Create CI Pipeline (GitHub Actions)

**`.github/workflows/ci.yml`**:

```yaml
name: Continuous Integration

on:
  push:
    branches: [ main, develop ]
  pull_request:
    branches: [ main, develop ]

env:
  DOTNET_VERSION: '8.0.x'
  NODE_VERSION: '20.x'

jobs:
  # Backend CI
  backend-ci:
    name: Backend CI
    runs-on: ubuntu-latest
    
    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Setup .NET
        uses: actions/setup-dotnet@v3
        with:
          dotnet-version: ${{ env.DOTNET_VERSION }}

      - name: Restore dependencies
        run: dotnet restore src/backend/Backend.sln

      - name: Build
        run: dotnet build src/backend/Backend.sln --configuration Release --no-restore

      - name: Run unit tests
        run: dotnet test tests/Api.Tests/Api.Tests.csproj --configuration Release --no-build --verbosity normal --collect:"XPlat Code Coverage"

      - name: Run integration tests
        run: dotnet test tests/Integration.Tests/Integration.Tests.csproj --configuration Release --no-build --verbosity normal

      - name: Generate code coverage report
        uses: codecov/codecov-action@v3
        with:
          files: '**/coverage.cobertura.xml'
          flags: backend
          name: backend-coverage

      - name: Check code coverage threshold
        run: |
          COVERAGE=$(grep -oP 'line-rate="\K[0-9.]+' tests/Api.Tests/coverage.cobertura.xml | head -1)
          COVERAGE_PERCENT=$(echo "$COVERAGE * 100" | bc)
          echo "Code coverage: $COVERAGE_PERCENT%"
          if (( $(echo "$COVERAGE_PERCENT < 80" | bc -l) )); then
            echo "Code coverage is below 80% threshold"
            exit 1
          fi

      - name: Run dotnet format check
        run: dotnet format src/backend/Backend.sln --verify-no-changes --verbosity diagnostic

      - name: Security scan
        run: dotnet list src/backend/Backend.sln package --vulnerable --include-transitive

  # Frontend CI
  frontend-ci:
    name: Frontend CI
    runs-on: ubuntu-latest
    
    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Setup Node.js
        uses: actions/setup-node@v4
        with:
          node-version: ${{ env.NODE_VERSION }}
          cache: 'npm'
          cache-dependency-path: src/frontend/package-lock.json

      - name: Install dependencies
        working-directory: src/frontend
        run: npm ci

      - name: Lint
        working-directory: src/frontend
        run: npm run lint

      - name: Format check
        working-directory: src/frontend
        run: npm run format -- --check

      - name: Type check
        working-directory: src/frontend
        run: npx tsc --noEmit

      - name: Run unit tests
        working-directory: src/frontend
        run: npm run test:coverage

      - name: Check code coverage threshold
        working-directory: src/frontend
        run: |
          COVERAGE=$(cat coverage/coverage-summary.json | jq '.total.lines.pct')
          echo "Code coverage: $COVERAGE%"
          if (( $(echo "$COVERAGE < 80" | bc -l) )); then
            echo "Code coverage is below 80% threshold"
            exit 1
          fi

      - name: Build
        working-directory: src/frontend
        run: npm run build

      - name: Upload build artifacts
        uses: actions/upload-artifact@v3
        with:
          name: frontend-dist
          path: src/frontend/dist

  # E2E Tests
  e2e-tests:
    name: End-to-End Tests
    runs-on: ubuntu-latest
    needs: [backend-ci, frontend-ci]
    
    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Setup .NET
        uses: actions/setup-dotnet@v3
        with:
          dotnet-version: ${{ env.DOTNET_VERSION }}

      - name: Setup Node.js
        uses: actions/setup-node@v4
        with:
          node-version: ${{ env.NODE_VERSION }}

      - name: Start services with Docker Compose
        run: docker-compose up -d

      - name: Wait for services to be healthy
        run: |
          timeout 60 bash -c 'until docker-compose ps | grep healthy; do sleep 5; done'

      - name: Run E2E tests
        run: |
          cd tests/E2E.Tests
          npm ci
          npx playwright install
          npx playwright test

      - name: Upload E2E test results
        if: always()
        uses: actions/upload-artifact@v3
        with:
          name: playwright-report
          path: tests/E2E.Tests/playwright-report

      - name: Stop services
        if: always()
        run: docker-compose down

  # Security scanning
  security-scan:
    name: Security Scan
    runs-on: ubuntu-latest
    
    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Run Trivy vulnerability scanner
        uses: aquasecurity/trivy-action@master
        with:
          scan-type: 'fs'
          scan-ref: '.'
          format: 'sarif'
          output: 'trivy-results.sarif'

      - name: Upload Trivy results to GitHub Security
        uses: github/codeql-action/upload-sarif@v2
        with:
          sarif_file: 'trivy-results.sarif'

  # Quality gates check
  quality-gates:
    name: Quality Gates
    runs-on: ubuntu-latest
    needs: [backend-ci, frontend-ci, e2e-tests, security-scan]
    
    steps:
      - name: All checks passed
        run: echo "All quality gates passed successfully!"
```

#### 3.2 Create CD Pipeline

**`.github/workflows/cd.yml`**:

```yaml
name: Continuous Deployment

on:
  push:
    branches: [ main ]
    tags:
      - 'v*'

env:
  REGISTRY: ghcr.io
  IMAGE_NAME: ${{ github.repository }}

jobs:
  build-and-push:
    name: Build and Push Docker Images
    runs-on: ubuntu-latest
    permissions:
      contents: read
      packages: write
    
    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Log in to Container Registry
        uses: docker/login-action@v3
        with:
          registry: ${{ env.REGISTRY }}
          username: ${{ github.actor }}
          password: ${{ secrets.GITHUB_TOKEN }}

      - name: Extract metadata for Backend
        id: meta-backend
        uses: docker/metadata-action@v5
        with:
          images: ${{ env.REGISTRY }}/${{ env.IMAGE_NAME }}/backend
          tags: |
            type=ref,event=branch
            type=ref,event=pr
            type=semver,pattern={{version}}
            type=semver,pattern={{major}}.{{minor}}
            type=sha

      - name: Build and push Backend image
        uses: docker/build-push-action@v5
        with:
          context: .
          file: infrastructure/docker/backend.Dockerfile
          push: true
          tags: ${{ steps.meta-backend.outputs.tags }}
          labels: ${{ steps.meta-backend.outputs.labels }}

      - name: Extract metadata for Frontend
        id: meta-frontend
        uses: docker/metadata-action@v5
        with:
          images: ${{ env.REGISTRY }}/${{ env.IMAGE_NAME }}/frontend
          tags: |
            type=ref,event=branch
            type=ref,event=pr
            type=semver,pattern={{version}}
            type=semver,pattern={{major}}.{{minor}}
            type=sha

      - name: Build and push Frontend image
        uses: docker/build-push-action@v5
        with:
          context: .
          file: infrastructure/docker/frontend.Dockerfile
          push: true
          tags: ${{ steps.meta-frontend.outputs.tags }}
          labels: ${{ steps.meta-frontend.outputs.labels }}

  deploy-staging:
    name: Deploy to Staging
    runs-on: ubuntu-latest
    needs: build-and-push
    if: github.ref == 'refs/heads/main'
    environment:
      name: staging
      url: https://staging.example.com
    
    steps:
      - name: Deploy to staging
        run: |
          echo "Deploy to staging environment"
          # Add your deployment commands here
          # e.g., kubectl apply, helm upgrade, etc.

  deploy-production:
    name: Deploy to Production
    runs-on: ubuntu-latest
    needs: build-and-push
    if: startsWith(github.ref, 'refs/tags/v')
    environment:
      name: production
      url: https://example.com
    
    steps:
      - name: Deploy to production
        run: |
          echo "Deploy to production environment"
          # Add your production deployment commands here
```

#### 3.3 Create Security Scanning Workflow

**`.github/workflows/security.yml`**:

```yaml
name: Security Scanning

on:
  schedule:
    - cron: '0 0 * * 0'  # Weekly on Sundays
  workflow_dispatch:

jobs:
  dependency-scan:
    name: Dependency Vulnerability Scan
    runs-on: ubuntu-latest
    
    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Run Snyk to check for vulnerabilities
        uses: snyk/actions/node@master
        continue-on-error: true
        env:
          SNYK_TOKEN: ${{ secrets.SNYK_TOKEN }}
        with:
          args: --severity-threshold=high

      - name: Dependabot alerts
        run: |
          echo "Dependabot is configured to scan for dependency vulnerabilities"
          echo "Check the Security tab in GitHub for alerts"

  code-scanning:
    name: Code Quality Scan
    runs-on: ubuntu-latest
    
    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Initialize CodeQL
        uses: github/codeql-action/init@v2
        with:
          languages: csharp, javascript

      - name: Autobuild
        uses: github/codeql-action/autobuild@v2

      - name: Perform CodeQL Analysis
        uses: github/codeql-action/analyze@v2
```

**Output**: Complete CI/CD pipeline with quality gates

---

## Step 4: Development Environment Setup (3-4 hours)

### Objective

Create automated developer onboarding with setup scripts and comprehensive documentation.

### Actions

#### 4.1 Create Setup Script for Unix/Mac

**`scripts/setup-dev.sh`**:

```bash
#!/bin/bash

# Development Environment Setup Script
# Run this script to set up your local development environment

set -e  # Exit on error

echo "=================================="
echo "Development Environment Setup"
echo "=================================="
echo ""

# Color codes for output
RED='\033[0;31m'
GREEN='\033[0;32m'
YELLOW='\033[1;33m'
NC='\033[0m' # No Color

# Check prerequisites
echo "Checking prerequisites..."

check_command() {
    if command -v $1 &> /dev/null; then
        echo -e "${GREEN}✓${NC} $1 is installed"
        return 0
    else
        echo -e "${RED}✗${NC} $1 is not installed"
        return 1
    fi
}

MISSING_DEPS=0

check_command "docker" || MISSING_DEPS=1
check_command "docker-compose" || MISSING_DEPS=1
check_command "dotnet" || MISSING_DEPS=1
check_command "node" || MISSING_DEPS=1
check_command "npm" || MISSING_DEPS=1

if [ $MISSING_DEPS -eq 1 ]; then
    echo -e "${RED}Please install missing dependencies and try again.${NC}"
    echo "Installation guides:"
    echo "  Docker: https://docs.docker.com/get-docker/"
    echo "  .NET SDK: https://dotnet.microsoft.com/download"
    echo "  Node.js: https://nodejs.org/"
    exit 1
fi

echo ""

# Check versions
echo "Checking versions..."
echo "Docker: $(docker --version)"
echo "Docker Compose: $(docker-compose --version)"
echo "dotnet: $(dotnet --version)"
echo "Node: $(node --version)"
echo "npm: $(npm --version)"
echo ""

# Copy environment file
echo "Setting up environment variables..."
if [ ! -f .env ]; then
    cp .env.example .env
    echo -e "${GREEN}✓${NC} Created .env file from .env.example"
    echo -e "${YELLOW}⚠${NC} Please review and update .env with your settings"
else
    echo -e "${YELLOW}⚠${NC} .env already exists, skipping"
fi
echo ""

# Install backend dependencies
echo "Installing backend dependencies..."
cd src/backend
dotnet restore
echo -e "${GREEN}✓${NC} Backend dependencies restored"
cd ../..
echo ""

# Install frontend dependencies
echo "Installing frontend dependencies..."
cd src/frontend
npm ci
echo -e "${GREEN}✓${NC} Frontend dependencies installed"
cd ../..
echo ""

# Start Docker services
echo "Starting Docker services..."
docker-compose up -d database cache
echo "Waiting for services to be ready..."
sleep 10
echo -e "${GREEN}✓${NC} Docker services started"
echo ""

# Run database migrations
echo "Running database migrations..."
cd src/backend
dotnet ef database update --project Infrastructure/Infrastructure.csproj --startup-project Api/Api.csproj
echo -e "${GREEN}✓${NC} Database migrations complete"
cd ../..
echo ""

# Seed test data (optional)
read -p "Do you want to seed test data? (y/N) " -n 1 -r
echo
if [[ $REPLY =~ ^[Yy]$ ]]; then
    echo "Seeding test data..."
    ./scripts/seed-data.sh
    echo -e "${GREEN}✓${NC} Test data seeded"
fi
echo ""

# Setup complete
echo "=================================="
echo -e "${GREEN}✓ Setup complete!${NC}"
echo "=================================="
echo ""
echo "Next steps:"
echo "  1. Review and update .env file if needed"
echo "  2. Start the backend: cd src/backend/Api && dotnet run"
echo "  3. Start the frontend: cd src/frontend && npm run dev"
echo "  4. Or use Docker: docker-compose up"
echo ""
echo "Useful commands:"
echo "  - View logs: docker-compose logs -f"
echo "  - Stop services: docker-compose down"
echo "  - Run tests: dotnet test (backend) or npm test (frontend)"
echo "  - Access pgAdmin: http://localhost:5050"
echo ""
echo "Documentation: See docs/development/getting-started.md"
```

#### 4.2 Create Setup Script for Windows

**`scripts/setup-dev.ps1`**:

```powershell
# Development Environment Setup Script for Windows
# Run this script to set up your local development environment

Write-Host "==================================" -ForegroundColor Cyan
Write-Host "Development Environment Setup" -ForegroundColor Cyan
Write-Host "==================================" -ForegroundColor Cyan
Write-Host ""

# Check prerequisites
Write-Host "Checking prerequisites..." -ForegroundColor Yellow

function Test-Command {
    param($Command)
    try {
        if (Get-Command $Command -ErrorAction Stop) {
            Write-Host "✓ $Command is installed" -ForegroundColor Green
            return $true
        }
    } catch {
        Write-Host "✗ $Command is not installed" -ForegroundColor Red
        return $false
    }
}

$missingDeps = 0
if (-not (Test-Command "docker")) { $missingDeps++ }
if (-not (Test-Command "docker-compose")) { $missingDeps++ }
if (-not (Test-Command "dotnet")) { $missingDeps++ }
if (-not (Test-Command "node")) { $missingDeps++ }
if (-not (Test-Command "npm")) { $missingDeps++ }

if ($missingDeps -gt 0) {
    Write-Host "Please install missing dependencies and try again." -ForegroundColor Red
    Write-Host "Installation guides:"
    Write-Host "  Docker: https://docs.docker.com/desktop/install/windows-install/"
    Write-Host "  .NET SDK: https://dotnet.microsoft.com/download"
    Write-Host "  Node.js: https://nodejs.org/"
    exit 1
}

Write-Host ""

# Check versions
Write-Host "Checking versions..." -ForegroundColor Yellow
Write-Host "Docker: $(docker --version)"
Write-Host "Docker Compose: $(docker-compose --version)"
Write-Host "dotnet: $(dotnet --version)"
Write-Host "Node: $(node --version)"
Write-Host "npm: $(npm --version)"
Write-Host ""

# Copy environment file
Write-Host "Setting up environment variables..." -ForegroundColor Yellow
if (-not (Test-Path .env)) {
    Copy-Item .env.example .env
    Write-Host "✓ Created .env file from .env.example" -ForegroundColor Green
    Write-Host "⚠ Please review and update .env with your settings" -ForegroundColor Yellow
} else {
    Write-Host "⚠ .env already exists, skipping" -ForegroundColor Yellow
}
Write-Host ""

# Install backend dependencies
Write-Host "Installing backend dependencies..." -ForegroundColor Yellow
Set-Location src\backend
dotnet restore
Write-Host "✓ Backend dependencies restored" -ForegroundColor Green
Set-Location ..\..
Write-Host ""

# Install frontend dependencies
Write-Host "Installing frontend dependencies..." -ForegroundColor Yellow
Set-Location src\frontend
npm ci
Write-Host "✓ Frontend dependencies installed" -ForegroundColor Green
Set-Location ..\..
Write-Host ""

# Start Docker services
Write-Host "Starting Docker services..." -ForegroundColor Yellow
docker-compose up -d database cache
Write-Host "Waiting for services to be ready..."
Start-Sleep -Seconds 10
Write-Host "✓ Docker services started" -ForegroundColor Green
Write-Host ""

# Run database migrations
Write-Host "Running database migrations..." -ForegroundColor Yellow
Set-Location src\backend
dotnet ef database update --project Infrastructure\Infrastructure.csproj --startup-project Api\Api.csproj
Write-Host "✓ Database migrations complete" -ForegroundColor Green
Set-Location ..\..
Write-Host ""

# Setup complete
Write-Host "==================================" -ForegroundColor Cyan
Write-Host "✓ Setup complete!" -ForegroundColor Green
Write-Host "==================================" -ForegroundColor Cyan
Write-Host ""
Write-Host "Next steps:"
Write-Host "  1. Review and update .env file if needed"
Write-Host "  2. Start the backend: cd src\backend\Api && dotnet run"
Write-Host "  3. Start the frontend: cd src\frontend && npm run dev"
Write-Host "  4. Or use Docker: docker-compose up"
Write-Host ""
Write-Host "Useful commands:"
Write-Host "  - View logs: docker-compose logs -f"
Write-Host "  - Stop services: docker-compose down"
Write-Host "  - Run tests: dotnet test (backend) or npm test (frontend)"
Write-Host "  - Access pgAdmin: http://localhost:5050"
Write-Host ""
Write-Host "Documentation: See docs\development\getting-started.md"
```

#### 4.3 Create Database Migration Script

**`scripts/migrate-db.sh`**:

```bash
#!/bin/bash

# Database Migration Script

set -e

echo "Running database migrations..."

cd src/backend

# Check if EF Core tools are installed
if ! dotnet ef &> /dev/null; then
    echo "Installing EF Core tools..."
    dotnet tool install --global dotnet-ef
fi

# Run migrations
dotnet ef database update \
    --project Infrastructure/Infrastructure.csproj \
    --startup-project Api/Api.csproj \
    --verbose

echo "✓ Migrations complete"
```

#### 4.4 Create Test Data Seeding Script

**`scripts/seed-data.sh`**:

```bash
#!/bin/bash

# Test Data Seeding Script

set -e

echo "Seeding test data..."

# Run seeding through API or direct database script
cd src/backend
dotnet run --project Api/Api.csproj -- seed-data

echo "✓ Test data seeded successfully"
```

**Output**: Complete developer onboarding automation

---

## Step 5: Documentation Generation (2-3 hours)

### Objective

Create comprehensive developer documentation for immediate productivity.

### Actions

#### 5.1 Create Main README

**`README.md`**:

```markdown
# [Project Name]

[Brief project description - what it does and why]

## 🚀 Quick Start

Get up and running in under 10 minutes:

```bash
# Clone the repository
git clone [repository-url]
cd [project-name]

# Run setup script
./scripts/setup-dev.sh  # Mac/Linux
# or
.\scripts\setup-dev.ps1  # Windows

# Start the application
docker-compose up
```

**Application URLs**:
- Frontend: http://localhost:3000
- Backend API: http://localhost:5000
- API Documentation: http://localhost:5000/swagger
- pgAdmin: http://localhost:5050

## 📋 Prerequisites

- **Docker** 24.0+ and Docker Compose 2.20+
- **.NET SDK** 8.0+
- **Node.js** 20.0+ (LTS)
- **Git** 2.40+

## 🏗️ Architecture

[Project Name] is built using:

- **Backend**: ASP.NET Core 8.0 Web API
- **Frontend**: React 18 with TypeScript and Vite
- **Database**: PostgreSQL 16
- **Cache**: Redis 7.2
- **Containerization**: Docker

See [docs/architecture](docs/architecture/) for detailed architecture documentation.

## 📦 Project Structure

```
project-root/
├── src/
│   ├── backend/        # C# backend services
│   └── frontend/       # React frontend app
├── tests/              # All test projects
├── infrastructure/     # Docker and IaC files
├── scripts/            # Utility scripts
└── docs/               # Documentation
```

## 🛠️ Development

### Running Locally

**Option 1: Docker Compose** (Recommended)
```bash
docker-compose up
```

**Option 2: Run Services Individually**
```bash
# Terminal 1 - Backend
cd src/backend/Api
dotnet run

# Terminal 2 - Frontend
cd src/frontend
npm run dev

# Terminal 3 - Database
docker-compose up database cache
```

### Running Tests

```bash
# Backend tests
dotnet test

# Frontend tests
cd src/frontend
npm test

# E2E tests
cd tests/E2E.Tests
npx playwright test
```

### Code Quality

```bash
# Format code
dotnet format                    # Backend
npm run format                   # Frontend

# Lint code
dotnet build                     # Backend (with analyzers)
npm run lint                     # Frontend

# Check coverage
dotnet test --collect:"XPlat Code Coverage"
npm run test:coverage
```

## 🚢 Deployment

See [docs/deployment](docs/deployment/) for deployment guides:

- [Docker deployment](docs/deployment/docker.md)
- [Kubernetes deployment](docs/deployment/kubernetes.md)
- [Cloud deployment](docs/deployment/cloud.md)

## 📚 Documentation

- [Getting Started](docs/development/getting-started.md)
- [API Documentation](docs/api/)
- [Architecture](docs/architecture/)
- [Contributing](CONTRIBUTING.md)

## 🤝 Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## 📄 License

[License type] - see [LICENSE](LICENSE) for details.

## 🙋 Support

- **Documentation**: [docs/](docs/)
- **Issues**: [GitHub Issues](https://github.com/[org]/[repo]/issues)
- **Discussions**: [GitHub Discussions](https://github.com/[org]/[repo]/discussions)
```

#### 5.2 Create Getting Started Guide

**`docs/development/getting-started.md`**:

```markdown
# Getting Started Guide

This guide will help you set up your development environment and start contributing to [Project Name].

## Prerequisites

Before you begin, ensure you have the following installed:

### Required

- **Docker Desktop** 24.0+
  - [Windows](https://docs.docker.com/desktop/install/windows-install/)
  - [Mac](https://docs.docker.com/desktop/install/mac-install/)
  - [Linux](https://docs.docker.com/desktop/install/linux-install/)

- **.NET SDK** 8.0+
  - [Download](https://dotnet.microsoft.com/download/dotnet/8.0)
  - Verify: `dotnet --version`

- **Node.js** 20.0+ (LTS)
  - [Download](https://nodejs.org/)
  - Verify: `node --version`

- **Git** 2.40+
  - [Download](https://git-scm.com/downloads)
  - Verify: `git --version`

### Recommended

- **IDE**: Visual Studio Code or Visual Studio 2022
- **Extensions** (VS Code):
  - C# Dev Kit
  - ESLint
  - Prettier
  - Docker
  - GitLens

## Initial Setup

### 1. Clone the Repository

```bash
git clone [repository-url]
cd [project-name]
```

### 2. Run Setup Script

**Mac/Linux:**
```bash
chmod +x scripts/setup-dev.sh
./scripts/setup-dev.sh
```

**Windows (PowerShell):**
```powershell
.\scripts\setup-dev.ps1
```

The setup script will:
- ✅ Check prerequisites
- ✅ Install dependencies
- ✅ Create `.env` file
- ✅ Start Docker services
- ✅ Run database migrations
- ✅ Optionally seed test data

### 3. Verify Installation

```bash
# Check Docker services are running
docker-compose ps

# All services should show "healthy" status
```

## Development Workflow

### Starting the Application

**Option 1: Docker Compose (Full Stack)**
```bash
docker-compose up

# Or in detached mode
docker-compose up -d
```

**Option 2: Individual Services**
```bash
# Terminal 1 - Database & Cache
docker-compose up database cache

# Terminal 2 - Backend
cd src/backend/Api
dotnet watch run

# Terminal 3 - Frontend
cd src/frontend
npm run dev
```

### Accessing the Application

- **Frontend**: http://localhost:3000
- **Backend API**: http://localhost:5000
- **Swagger UI**: http://localhost:5000/swagger
- **pgAdmin**: http://localhost:5050 (admin@example.com / admin)

### Making Changes

1. **Create a feature branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

2. **Make your changes**
   - Backend: `src/backend/`
   - Frontend: `src/frontend/src/`

3. **Run tests**
   ```bash
   # Backend
   dotnet test
   
   # Frontend
   cd src/frontend
   npm test
   ```

4. **Check code quality**
   ```bash
   # Format
   dotnet format
   npm run format
   
   # Lint
   dotnet build
   npm run lint
   ```

5. **Commit and push**
   ```bash
   git add .
   git commit -m "feat: your feature description"
   git push origin feature/your-feature-name
   ```

6. **Create pull request**
   - Go to GitHub and create a PR
   - Wait for CI/CD checks to pass
   - Request review from team members

### Database Migrations

**Create new migration:**
```bash
cd src/backend
dotnet ef migrations add YourMigrationName --project Infrastructure/Infrastructure.csproj --startup-project Api/Api.csproj
```

**Apply migrations:**
```bash
dotnet ef database update --project Infrastructure/Infrastructure.csproj --startup-project Api/Api.csproj
```

**Rollback migration:**
```bash
dotnet ef database update PreviousMigrationName --project Infrastructure/Infrastructure.csproj --startup-project Api/Api.csproj
```

### Debugging

**Backend (VS Code)**:
1. Set breakpoints in C# code
2. Press F5 or use "Run and Debug" panel
3. Select ".NET Core Launch (web)" configuration

**Frontend (VS Code)**:
1. Set breakpoints in TypeScript/React code
2. Use browser developer tools
3. Or use VS Code debugger with Chrome

**Database**:
- Use pgAdmin at http://localhost:5050
- Or connect with your favorite SQL client:
  - Host: localhost
  - Port: 5432
  - Database: projectdb
  - User: postgres
  - Password: (from .env)

## Common Tasks

### Reset Database

```bash
docker-compose down -v
docker-compose up -d database
./scripts/migrate-db.sh
./scripts/seed-data.sh
```

### View Logs

```bash
# All services
docker-compose logs -f

# Specific service
docker-compose logs -f backend
```

### Update Dependencies

```bash
# Backend
cd src/backend
dotnet restore

# Frontend
cd src/frontend
npm update
```

### Clean Build

```bash
# Backend
cd src/backend
dotnet clean
dotnet build

# Frontend
cd src/frontend
rm -rf node_modules dist
npm ci
npm run build
```

## Troubleshooting

### "Port already in use"

```bash
# Find process using port
lsof -i :5000   # Mac/Linux
netstat -ano | findstr :5000   # Windows

# Stop Docker services
docker-compose down
```

### "Database connection failed"

```bash
# Restart database
docker-compose restart database

# Check database logs
docker-compose logs database

# Verify connection in .env file
```

### "Module not found" (Frontend)

```bash
cd src/frontend
rm -rf node_modules package-lock.json
npm install
```

### "Build failed" (Backend)

```bash
cd src/backend
dotnet clean
dotnet restore
dotnet build
```

## Next Steps

- [ ] Read [Architecture Documentation](../architecture/)
- [ ] Review [API Documentation](../api/)
- [ ] Check [Contributing Guidelines](../../CONTRIBUTING.md)
- [ ] Join team Slack/Discord channel
- [ ] Attend team standup meetings

## Getting Help

- **Documentation**: Check [docs/](../)
- **Issues**: Search [GitHub Issues](https://github.com/[org]/[repo]/issues)
- **Team**: Ask in Slack/Discord
- **Code Reviews**: Learn from PR feedback

Happy coding! 🚀
```

#### 5.3 Create Contributing Guide

**`CONTRIBUTING.md`**:

```markdown
# Contributing to [Project Name]

Thank you for your interest in contributing! This document provides guidelines and workflows for contributing to the project.

## Code of Conduct

Be respectful, inclusive, and professional in all interactions.

## Getting Started

1. Fork the repository
2. Clone your fork
3. Follow the [Getting Started Guide](docs/development/getting-started.md)
4. Create a feature branch

## Development Workflow

### Branch Naming

- `feature/` - New features
- `fix/` - Bug fixes
- `docs/` - Documentation changes
- `refactor/` - Code refactoring
- `test/` - Test additions/changes

Example: `feature/user-authentication`

### Commit Messages

Follow [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>(<scope>): <description>

[optional body]

[optional footer]
```

**Types:**
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation
- `style`: Formatting
- `refactor`: Code restructuring
- `test`: Tests
- `chore`: Maintenance

**Examples:**
```
feat(auth): add JWT token validation
fix(api): resolve null reference in user endpoint
docs(readme): update installation instructions
```

### Pull Request Process

1. **Update from main**
   ```bash
   git fetch upstream
   git rebase upstream/main
   ```

2. **Run all quality checks**
   ```bash
   # Format
   dotnet format
   npm run format
   
   # Lint
   dotnet build
   npm run lint
   
   # Tests
   dotnet test
   npm test
   
   # Coverage
   dotnet test --collect:"XPlat Code Coverage"
   npm run test:coverage
   ```

3. **Create pull request**
   - Write clear title and description
   - Link related issues
   - Add screenshots (if UI changes)
   - Request reviewers

4. **Address review feedback**
   - Make requested changes
   - Push to same branch
   - Reply to review comments

5. **Merge**
   - Wait for approval
   - CI/CD must pass
   - Squash and merge

## Code Standards

### C# Backend

- Follow [C# Coding Conventions](https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style/coding-conventions)
- Use `dotnet format` for formatting
- Enable nullable reference types
- Use async/await for I/O operations
- Write XML documentation for public APIs

**Example:**
```csharp
/// <summary>
/// Gets a user by their unique identifier.
/// </summary>
/// <param name="userId">The user's ID.</param>
/// <returns>The user if found; otherwise null.</returns>
public async Task<User?> GetUserByIdAsync(Guid userId)
{
    return await _context.Users
        .FirstOrDefaultAsync(u => u.Id == userId);
}
```

### TypeScript/React Frontend

- Follow [Airbnb React Style Guide](https://github.com/airbnb/javascript/tree/master/react)
- Use functional components with hooks
- Use TypeScript for type safety
- Use Prettier for formatting
- Use ESLint for linting

**Example:**
```typescript
interface UserProfileProps {
  userId: string;
}

export const UserProfile: React.FC<UserProfileProps> = ({ userId }) => {
  const [user, setUser] = useState<User | null>(null);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    fetchUser(userId);
  }, [userId]);

  // Component logic...
};
```

### Testing Standards

**Test Coverage:**
- Unit tests: >80% coverage required
- Integration tests: Critical paths
- E2E tests: User workflows

**Backend Testing:**
```csharp
[Fact]
public async Task GetUserById_WhenUserExists_ReturnsUser()
{
    // Arrange
    var userId = Guid.NewGuid();
    var expectedUser = new User { Id = userId, Name = "Test" };
    _mockRepository.Setup(r => r.GetByIdAsync(userId))
        .ReturnsAsync(expectedUser);

    // Act
    var result = await _service.GetUserByIdAsync(userId);

    // Assert
    Assert.NotNull(result);
    Assert.Equal(expectedUser.Name, result.Name);
}
```

**Frontend Testing:**
```typescript
describe('UserProfile', () => {
  it('displays user information when loaded', async () => {
    const mockUser = { id: '1', name: 'Test User' };
    jest.spyOn(api, 'fetchUser').mockResolvedValue(mockUser);

    render(<UserProfile userId="1" />);

    await waitFor(() => {
      expect(screen.getByText('Test User')).toBeInTheDocument();
    });
  });
});
```

## Documentation

- Update README.md for major changes
- Add/update API documentation
- Include code comments for complex logic
- Update architecture docs if needed

## Release Process

1. Version bump in all package files
2. Update CHANGELOG.md
3. Create git tag: `v1.2.3`
4. Push tag triggers CD pipeline
5. Verify deployment to staging
6. Promote to production

## Questions?

- Check [documentation](docs/)
- Search [existing issues](https://github.com/[org]/[repo]/issues)
- Ask in team chat
- Create a new issue

Thank you for contributing! 🎉
```

**Output**: Complete developer documentation

---

## Step 6: Infrastructure Validation (2-3 hours)

### Objective

Verify that the entire infrastructure is functional and ready for Phase 3 development.

### Actions

#### 6.1 Run Infrastructure Tests

```bash
# Test 1: Repository structure exists
echo "✓ Checking repository structure..."
test -d src/backend && echo "  ✓ Backend directory exists"
test -d src/frontend && echo "  ✓ Frontend directory exists"
test -d tests && echo "  ✓ Tests directory exists"
test -d infrastructure && echo "  ✓ Infrastructure directory exists"

# Test 2: Configuration files exist
echo "✓ Checking configuration files..."
test -f docker-compose.yml && echo "  ✓ docker-compose.yml exists"
test -f .gitignore && echo "  ✓ .gitignore exists"
test -f .editorconfig && echo "  ✓ .editorconfig exists"
test -f .env.example && echo "  ✓ .env.example exists"

# Test 3: Docker containers build
echo "✓ Building Docker images..."
docker-compose build

# Test 4: Docker containers start
echo "✓ Starting Docker containers..."
docker-compose up -d

# Test 5: Health checks pass
echo "✓ Waiting for health checks..."
sleep 30
docker-compose ps | grep healthy

# Test 6: Backend responds
echo "✓ Testing backend..."
curl -f http://localhost:5000/health || echo "  ✗ Backend health check failed"

# Test 7: Frontend responds
echo "✓ Testing frontend..."
curl -f http://localhost:3000 || echo "  ✗ Frontend health check failed"

# Test 8: Database is accessible
echo "✓ Testing database..."
docker-compose exec database pg_isready -U postgres

# Test 9: Run backend tests
echo "✓ Running backend tests..."
cd src/backend
dotnet test

# Test 10: Run frontend tests
echo "✓ Running frontend tests..."
cd ../frontend
npm test -- --run

# Cleanup
cd ../..
docker-compose down
```

#### 6.2 Create Validation Checklist

**`artifacts/infrastructure-validation.md`**:

```markdown
# Infrastructure Validation Checklist

**Project**: [Project Name]  
**Date**: [YYYY-MM-DD]  
**Validated By**: [Name]

## Repository Structure

- [ ] All directories created per repository structure template
- [ ] `.gitignore` configured and working
- [ ] `.editorconfig` configured
- [ ] `.env.example` created (`.env` is gitignored)
- [ ] README.md is complete and accurate
- [ ] CONTRIBUTING.md provides clear guidelines

## Build Configuration

- [ ] Backend solution builds successfully (`dotnet build`)
- [ ] Frontend builds successfully (`npm run build`)
- [ ] No compilation errors or warnings
- [ ] Linting passes (`dotnet format --verify`, `npm run lint`)
- [ ] Project references are correct

## Docker Configuration

- [ ] `docker-compose.yml` is valid
- [ ] All Dockerfiles build successfully
- [ ] All containers start successfully
- [ ] Health checks pass for all services
- [ ] Services can communicate with each other
- [ ] Volume mounts work correctly
- [ ] Environment variables are injected correctly

## Database

- [ ] PostgreSQL container starts successfully
- [ ] Database migrations run successfully
- [ ] Can connect to database from backend
- [ ] Can connect to database with pgAdmin
- [ ] Test data seeding works (if applicable)

## Backend API

- [ ] API starts successfully
- [ ] Health endpoint responds: `http://localhost:5000/health`
- [ ] Swagger UI accessible: `http://localhost:5000/swagger`
- [ ] Can make API requests successfully
- [ ] Authentication/authorization configured (if applicable)
- [ ] CORS configured correctly for frontend

## Frontend Application

- [ ] Frontend starts successfully
- [ ] Can access at `http://localhost:3000`
- [ ] Hot reload works
- [ ] Can make API requests to backend
- [ ] Environment variables loaded correctly
- [ ] No console errors on load

## Testing Infrastructure

- [ ] Unit test projects configured
- [ ] Unit tests run successfully (`dotnet test`, `npm test`)
- [ ] Code coverage reports generated
- [ ] Integration test infrastructure works
- [ ] E2E test infrastructure configured (Playwright)
- [ ] Test data setup/teardown works

## CI/CD Pipeline

- [ ] `.github/workflows/ci.yml` is valid
- [ ] CI pipeline runs on push/PR
- [ ] All CI jobs complete successfully
- [ ] Quality gates enforce standards
- [ ] Code coverage thresholds enforced
- [ ] Security scanning configured
- [ ] CD pipeline configured (if applicable)

## Developer Experience

- [ ] Setup script works: `./scripts/setup-dev.sh`
- [ ] Can clone and run in < 10 minutes
- [ ] Documentation is clear and complete
- [ ] Common commands are documented
- [ ] Troubleshooting guide is helpful
- [ ] IDE configurations work (VS Code/Visual Studio)

## Documentation

- [ ] README.md complete and accurate
- [ ] Getting Started guide is comprehensive
- [ ] API documentation available
- [ ] Architecture docs copied from Phase 1
- [ ] Deployment guides created (or marked as TODO)
- [ ] CONTRIBUTING.md provides clear guidelines

## Quality & Security

- [ ] Code formatting enforced
- [ ] Linting configured and passing
- [ ] Security scanning configured (Dependabot, Snyk)
- [ ] HTTPS enforced in production config
- [ ] Secrets not committed to repository
- [ ] `.env` is gitignored

## Performance

- [ ] Docker images are reasonably sized
- [ ] Build times are acceptable (< 5 min)
- [ ] Hot reload latency is acceptable (< 3 sec)
- [ ] API response times are reasonable (< 500ms for simple requests)

## Sign-off

**Infrastructure is ready for Phase 3 development**: ✅ Yes / ❌ No

**Validator Signature**: [Name] - [Date]  
**Tech Lead Signature**: [Name] - [Date]  
**DevOps Lead Signature**: [Name] - [Date]

**Notes**:
[Any issues, concerns, or follow-up items]
```

#### 6.3 Update Phase 2 Session Metadata

Update `session.meta.md` with completion status:

```markdown
## Infrastructure Setup Complete

**Completion Date**: [YYYY-MM-DD]  
**Time Taken**: [X] days  
**Validated By**: [Name]

### Deliverables

- âœ… Repository structure created
- ✅ Docker containerization configured
- ✅ CI/CD pipeline functional
- ✅ Development environment automated
- ✅ Documentation complete
- ✅ Infrastructure validated

### Metrics

- **Clone to Code Time**: [X] minutes
- **Docker Build Time**: [X] minutes
- **CI Pipeline Duration**: [X] minutes
- **Test Execution Time**: [X] seconds

### Next Steps

- Phase 2 validation with Validator Agent
- Phase 2 completion checklist
- Handoff to Phase 3 development team
```

**Output**: Validated, production-ready development infrastructure

---

## Success Criteria

This repository setup workflow is complete when:

âœ… **Repository is functional**: Can clone, build, and run successfully  
✅ **Docker works**: All services containerized and orchestrated  
✅ **CI/CD operational**: Pipeline runs and enforces quality gates  
✅ **Developer-friendly**: Setup takes < 10 minutes for new developers  
✅ **Well-documented**: Comprehensive docs for all aspects  
✅ **Quality enforced**: Automated linting, testing, security scanning  
âœ… **Validated**: All validation checks pass

---

## Handoff to Phase 3

With repository setup complete, you're ready for Phase 3 development:

**What Phase 3 Needs**:
1. ✅ Working repository (can clone and run immediately)
2. ✅ Development environment (Docker, IDE, tools configured)
3. ✅ CI/CD pipeline (automated quality gates)
4. ✅ Documentation (how to develop, test, deploy)
5. ✅ Quality standards (enforced via tooling)

**Handoff Artifacts**:
- Repository URL and access instructions
- `.env.example` file (developers create their own `.env`)
- Setup script (one-command environment setup)
- Developer documentation (getting started, contributing)
- CI/CD pipeline (already running on GitHub)

**Developer Onboarding Time**: < 10 minutes from clone to first successful run

---

*This workflow ensures a production-ready development infrastructure that enables immediate productivity in Phase 3.*
