# Repository Structure

**Project Name**: [Project name from constitution]  
**Date Created**: [YYYY-MM-DD]  
**Last Updated**: [YYYY-MM-DD]  
**Version**: [v1.0, v2.0, etc.]  
**Created By**: [DevOps Scaffolder / Infrastructure Lead]  
**Technology Stack**: [Backend language + Frontend framework]

---

## Purpose of This Document

This Repository Structure document defines the **standardized organization of all code, configuration, documentation, and infrastructure** for the project. It serves as the authoritative reference for where files belong and how the codebase is organized.

**What This Document Contains**:
- Complete directory tree structure
- Purpose and contents of each directory
- Naming conventions and patterns
- File organization principles
- Technology-specific structures
- Configuration file locations
- Documentation organization

**What This Document Does NOT Contain**:
- Actual code or implementation details
- Docker or deployment configuration (see environment-config.md)
- CI/CD pipeline definitions (see .github/workflows/)
- Development setup instructions (see docs/development/)

**Who Uses This Document**:
- Developers: Know where to find and place files
- DevOps Engineers: Understand project organization for automation
- New Team Members: Quickly navigate the codebase
- Code Reviewers: Validate files are in correct locations
- Build Systems: Locate source and configuration files

**Traceability**:
- **From**: architecture.md (component structure), technology-stack.md (tech choices)
- **To**: Actual repository file organization
- **Related**: environment-config.md, repository-setup.prompt.md

---

## Repository Overview

**Repository Type**: [Monorepo / Multi-repo]  
**Primary Languages**: [e.g., C#, TypeScript]  
**Total Directory Count**: [Approximate number]  
**Organization Principle**: [e.g., By component, by layer, by feature]

---

## High-Level Structure

```
[project-name]/
├── .github/              # GitHub-specific configuration and workflows
├── .vscode/              # VS Code workspace settings (optional)
├── docs/                 # All project documentation
├── src/                  # All source code
├── tests/                # All test projects
├── scripts/              # Utility and automation scripts
├── infrastructure/       # Infrastructure as Code and Docker files
├── .editorconfig         # Editor configuration
├── .gitignore            # Git ignore rules
├── .env.example          # Environment variable template
├── docker-compose.yml    # Docker orchestration
├── README.md             # Project overview and quick start
├── CONTRIBUTING.md       # Contribution guidelines
└── LICENSE               # License file
```

---

## Directory Specifications

### `.github/` - GitHub Configuration

**Purpose**: GitHub-specific configuration, workflows, and templates

```
.github/
├── workflows/                    # GitHub Actions CI/CD workflows
│   ├── ci.yml                   # Continuous integration (build, test, lint)
│   ├── cd.yml                   # Continuous deployment
│   ├── security.yml             # Security scanning
│   └── pr-checks.yml            # Pull request validation
├── ISSUE_TEMPLATE/              # Issue templates
│   ├── bug_report.md            # Bug report template
│   ├── feature_request.md       # Feature request template
│   └── config.yml               # Issue template configuration
├── PULL_REQUEST_TEMPLATE.md     # PR template
└── dependabot.yml               # Dependabot configuration
```

**Key Files**:
- `workflows/*.yml`: CI/CD pipeline definitions
- `ISSUE_TEMPLATE/`: Standardized issue reporting
- `PULL_REQUEST_TEMPLATE.md`: PR description guidance

**Naming Conventions**:
- Workflow files: `kebab-case.yml`
- Template files: `snake_case.md`

---

### `.vscode/` - VS Code Workspace Settings (Optional)

**Purpose**: Team-shared VS Code configuration for consistent development experience

```
.vscode/
├── settings.json          # Workspace settings
├── launch.json           # Debug configurations
├── tasks.json            # Custom tasks
└── extensions.json       # Recommended extensions
```

**When to Use**:
- Include if team primarily uses VS Code
- Gitignore personal settings, commit team settings
- Alternative: `.idea/` for JetBrains IDEs

**Example `settings.json`**:
```json
{
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  },
  "files.exclude": {
    "**/bin": true,
    "**/obj": true,
    "**/node_modules": true
  }
}
```

---

### `docs/` - Documentation

**Purpose**: All project documentation organized by audience and purpose

```
docs/
├── architecture/                # Architecture documentation (from Phase 1)
│   ├── overview.md             # Architecture overview
│   ├── components.md           # Component descriptions
│   ├── data-flow.md            # Data flow diagrams
│   ├── c4-diagrams/            # C4 model diagrams
│   └── decisions/              # Architecture Decision Records (ADRs)
│       ├── 001-use-postgresql.md
│       ├── 002-react-frontend.md
│       └── template.md
├── api/                        # API documentation
│   ├── overview.md             # API overview
│   ├── authentication.md       # Auth documentation
│   ├── endpoints/              # Endpoint documentation
│   │   ├── users.md
│   │   ├── products.md
│   │   └── orders.md
│   └── examples/               # API usage examples
├── development/                # Developer guides
│   ├── getting-started.md      # Setup and onboarding
│   ├── coding-standards.md     # Code style and conventions
│   ├── testing.md              # Testing guidelines
│   ├── debugging.md            # Debugging tips
│   └── troubleshooting.md      # Common issues and solutions
├── deployment/                 # Deployment documentation
│   ├── docker.md               # Docker deployment
│   ├── kubernetes.md           # K8s deployment
│   ├── cloud.md                # Cloud provider deployment
│   └── monitoring.md           # Monitoring and observability
├── user-guides/                # End-user documentation
│   ├── user-manual.md          # User manual
│   └── faq.md                  # Frequently asked questions
└── phase1-artifacts/           # Phase 1 deliverables (archived)
    ├── constitution.md
    ├── spec.md
    ├── prd.md
    └── data-model.md
```

**Organization Principles**:
- **By audience**: Separate developer docs from user docs
- **By purpose**: Architecture separate from API docs
- **Chronological**: Phase artifacts archived but accessible
- **Searchable**: Clear naming, linked index

**Key Files**:
- `architecture/overview.md`: High-level system design
- `development/getting-started.md`: New developer onboarding
- `api/`: Complete API reference

---

### `src/` - Source Code

**Purpose**: All application source code organized by component/layer

#### Option 1: Backend + Frontend Monorepo (C# + React Example)

```
src/
├── backend/                    # C# backend services
│   ├── Api/                   # Web API project (presentation layer)
│   │   ├── Controllers/       # API controllers
│   │   │   ├── UsersController.cs
│   │   │   ├── ProductsController.cs
│   │   │   └── OrdersController.cs
│   │   ├── Models/            # DTOs and request/response models
│   │   │   ├── Requests/
│   │   │   │   ├── CreateUserRequest.cs
│   │   │   │   └── UpdateUserRequest.cs
│   │   │   └── Responses/
│   │   │       ├── UserResponse.cs
│   │   │       └── ErrorResponse.cs
│   │   ├── Middleware/        # Custom middleware
│   │   │   ├── ErrorHandlingMiddleware.cs
│   │   │   └── LoggingMiddleware.cs
│   │   ├── Filters/           # Action filters
│   │   ├── Validators/        # Request validators
│   │   ├── Program.cs         # Application entry point
│   │   ├── Startup.cs         # Service configuration (if separate)
│   │   ├── appsettings.json   # Application settings
│   │   ├── appsettings.Development.json
│   │   ├── appsettings.Production.json
│   │   └── Api.csproj         # Project file
│   │
│   ├── Core/                  # Core domain logic (domain layer)
│   │   ├── Entities/          # Domain entities
│   │   │   ├── User.cs
│   │   │   ├── Product.cs
│   │   │   └── Order.cs
│   │   ├── Interfaces/        # Abstractions and contracts
│   │   │   ├── IUserRepository.cs
│   │   │   ├── IProductRepository.cs
│   │   │   └── IEmailService.cs
│   │   ├── Services/          # Domain services (business logic)
│   │   │   ├── UserService.cs
│   │   │   ├── OrderService.cs
│   │   │   └── PricingService.cs
│   │   ├── Exceptions/        # Domain exceptions
│   │   │   ├── UserNotFoundException.cs
│   │   │   └── InvalidOrderException.cs
│   │   ├── Enums/             # Domain enumerations
│   │   └── Core.csproj        # Project file
│   │
│   ├── Infrastructure/        # Infrastructure concerns (infrastructure layer)
│   │   ├── Data/              # Database context and repositories
│   │   │   ├── ApplicationDbContext.cs
│   │   │   ├── Repositories/
│   │   │   │   ├── UserRepository.cs
│   │   │   │   ├── ProductRepository.cs
│   │   │   │   └── OrderRepository.cs
│   │   │   ├── Configurations/ # Entity configurations
│   │   │   │   ├── UserConfiguration.cs
│   │   │   │   └── ProductConfiguration.cs
│   │   │   └── Migrations/    # EF Core migrations
│   │   ├── Services/          # External service implementations
│   │   │   ├── EmailService.cs
│   │   │   ├── CacheService.cs
│   │   │   └── PaymentService.cs
│   │   ├── Authentication/    # Auth implementation
│   │   │   ├── JwtTokenService.cs
│   │   │   └── PasswordHasher.cs
│   │   └── Infrastructure.csproj
│   │
│   └── Backend.sln            # Solution file
│
└── frontend/                  # React frontend application
    ├── public/                # Static assets
    │   ├── index.html         # HTML template
    │   ├── favicon.ico        # Favicon
    │   └── assets/            # Images, fonts, etc.
    │
    ├── src/                   # Frontend source code
    │   ├── components/        # Reusable React components
    │   │   ├── common/        # Common UI components
    │   │   │   ├── Button.tsx
    │   │   │   ├── Input.tsx
    │   │   │   ├── Modal.tsx
    │   │   │   └── LoadingSpinner.tsx
    │   │   ├── layout/        # Layout components
    │   │   │   ├── Header.tsx
    │   │   │   ├── Footer.tsx
    │   │   │   ├── Sidebar.tsx
    │   │   │   └── MainLayout.tsx
    │   │   └── features/      # Feature-specific components
    │   │       ├── users/
    │   │       │   ├── UserList.tsx
    │   │       │   ├── UserCard.tsx
    │   │       │   └── UserForm.tsx
    │   │       └── products/
    │   │           ├── ProductList.tsx
    │   │           └── ProductCard.tsx
    │   │
    │   ├── pages/             # Page components (route-level)
    │   │   ├── HomePage.tsx
    │   │   ├── LoginPage.tsx
    │   │   ├── DashboardPage.tsx
    │   │   ├── UsersPage.tsx
    │   │   └── NotFoundPage.tsx
    │   │
    │   ├── services/          # API service layer
    │   │   ├── api.ts         # Axios instance and config
    │   │   ├── userService.ts # User API calls
    │   │   ├── productService.ts
    │   │   └── authService.ts
    │   │
    │   ├── hooks/             # Custom React hooks
    │   │   ├── useAuth.ts     # Authentication hook
    │   │   ├── useApi.ts      # API call hook
    │   │   └── useLocalStorage.ts
    │   │
    │   ├── contexts/          # React contexts
    │   │   ├── AuthContext.tsx
    │   │   └── ThemeContext.tsx
    │   │
    │   ├── utils/             # Utility functions
    │   │   ├── formatters.ts  # Formatting utilities
    │   │   ├── validators.ts  # Validation utilities
    │   │   └── constants.ts   # Constants
    │   │
    │   ├── types/             # TypeScript type definitions
    │   │   ├── user.types.ts
    │   │   ├── product.types.ts
    │   │   └── api.types.ts
    │   │
    │   ├── styles/            # Global styles
    │   │   ├── index.css      # Global CSS
    │   │   └── theme.ts       # Theme configuration (if using MUI)
    │   │
    │   ├── routes/            # Routing configuration
    │   │   └── AppRoutes.tsx  # Route definitions
    │   │
    │   ├── App.tsx            # Root component
    │   ├── main.tsx           # Application entry point
    │   └── vite-env.d.ts      # Vite type definitions
    │
    ├── .eslintrc.json         # ESLint configuration
    ├── .prettierrc            # Prettier configuration
    ├── package.json           # Dependencies and scripts
    ├── tsconfig.json          # TypeScript configuration
    ├── tsconfig.node.json     # TypeScript config for Node scripts
    ├── vite.config.ts         # Vite build configuration
    └── README.md              # Frontend-specific documentation
```

#### Option 2: Microservices Architecture

```
src/
├── services/
│   ├── user-service/
│   │   ├── src/
│   │   ├── tests/
│   │   └── Dockerfile
│   ├── product-service/
│   │   ├── src/
│   │   ├── tests/
│   │   └── Dockerfile
│   └── order-service/
│       ├── src/
│       ├── tests/
│       └── Dockerfile
├── shared/
│   └── common/
└── api-gateway/
```

**Naming Conventions**:
- **C# Files**: PascalCase (e.g., `UserService.cs`)
- **TypeScript Files**: camelCase (e.g., `userService.ts`)
- **Components**: PascalCase (e.g., `UserCard.tsx`)
- **Hooks**: camelCase with 'use' prefix (e.g., `useAuth.ts`)
- **Directories**: kebab-case (e.g., `user-management/`)

**Key Principles**:
- **Separation of Concerns**: Clear layer boundaries (API, Core, Infrastructure)
- **Feature Organization**: Group related files together
- **Testability**: Easy to mock dependencies via interfaces
- **Scalability**: Structure supports growth

---

### `tests/` - Test Projects

**Purpose**: All automated tests organized by type and scope

```
tests/
├── Api.Tests/                 # API unit tests
│   ├── Controllers/           # Controller tests
│   │   ├── UsersControllerTests.cs
│   │   └── ProductsControllerTests.cs
│   ├── Validators/            # Validator tests
│   └── Api.Tests.csproj
│
├── Core.Tests/                # Core domain logic tests
│   ├── Services/              # Service tests
│   │   ├── UserServiceTests.cs
│   │   └── OrderServiceTests.cs
│   ├── Entities/              # Entity tests
│   └── Core.Tests.csproj
│
├── Infrastructure.Tests/      # Infrastructure tests
│   ├── Repositories/          # Repository tests
│   ├── Services/              # External service tests
│   └── Infrastructure.Tests.csproj
│
├── Integration.Tests/         # Integration tests
│   ├── Api/                   # API integration tests
│   │   ├── UserEndpointsTests.cs
│   │   └── AuthenticationTests.cs
│   ├── Database/              # Database integration tests
│   ├── Fixtures/              # Test fixtures and setup
│   │   ├── WebApplicationFactory.cs
│   │   └── DatabaseFixture.cs
│   └── Integration.Tests.csproj
│
├── E2E.Tests/                 # End-to-end tests (Playwright)
│   ├── tests/                 # Test files
│   │   ├── login.spec.ts
│   │   ├── user-management.spec.ts
│   │   └── checkout.spec.ts
│   ├── page-objects/          # Page object models
│   │   ├── LoginPage.ts
│   │   └── DashboardPage.ts
│   ├── fixtures/              # Test fixtures
│   ├── playwright.config.ts   # Playwright configuration
│   ├── package.json
│   └── README.md
│
└── Frontend.Tests/            # Frontend unit tests
    ├── components/            # Component tests
    │   ├── Button.test.tsx
    │   └── UserCard.test.tsx
    ├── hooks/                 # Hook tests
    ├── utils/                 # Utility function tests
    └── setup.ts               # Test setup and configuration
```

**Test Organization Principles**:
- **Mirror Source Structure**: Test structure mirrors src/ structure
- **By Test Type**: Separate unit, integration, E2E tests
- **Naming Convention**: `[ClassName]Tests.cs` or `[component].test.tsx`
- **Shared Utilities**: Common fixtures and helpers in dedicated folders

**Key Files**:
- `*/Fixtures/`: Shared test setup and data
- `E2E.Tests/playwright.config.ts`: E2E test configuration
- `Frontend.Tests/setup.ts`: Test environment setup

---

### `scripts/` - Utility Scripts

**Purpose**: Automation scripts for common development and deployment tasks

```
scripts/
├── setup-dev.sh              # Development environment setup (Unix/Mac)
├── setup-dev.ps1             # Development environment setup (Windows)
├── migrate-db.sh             # Database migration runner
├── seed-data.sh              # Test data seeding
├── backup-db.sh              # Database backup
├── restore-db.sh             # Database restore
├── build-all.sh              # Build all projects
├── test-all.sh               # Run all tests
├── deploy-staging.sh         # Deploy to staging
├── deploy-production.sh      # Deploy to production
├── clean.sh                  # Clean build artifacts
└── README.md                 # Script documentation
```

**Script Naming Conventions**:
- Use `.sh` for Unix/Mac shell scripts
- Use `.ps1` for Windows PowerShell scripts
- Use kebab-case for filenames
- Make scripts executable: `chmod +x script-name.sh`

**Script Standards**:
- Include shebang: `#!/bin/bash`
- Set error handling: `set -e` (exit on error)
- Add help text: `--help` flag
- Log actions with echo statements
- Use colored output for clarity

---

### `infrastructure/` - Infrastructure as Code

**Purpose**: Docker configurations, Kubernetes manifests, and IaC definitions

```
infrastructure/
├── docker/                    # Docker-related files
│   ├── backend.Dockerfile     # Backend container image
│   ├── frontend.Dockerfile    # Frontend container image
│   ├── nginx.conf             # nginx configuration
│   └── .dockerignore          # Docker ignore rules
│
├── k8s/                       # Kubernetes manifests (if applicable)
│   ├── base/                  # Base configurations
│   │   ├── deployment.yaml
│   │   ├── service.yaml
│   │   └── configmap.yaml
│   ├── overlays/              # Environment-specific overlays
│   │   ├── development/
│   │   ├── staging/
│   │   └── production/
│   └── kustomization.yaml
│
├── terraform/                 # Terraform IaC (if applicable)
│   ├── modules/               # Reusable modules
│   │   ├── database/
│   │   ├── networking/
│   │   └── compute/
│   ├── environments/          # Environment configs
│   │   ├── dev/
│   │   ├── staging/
│   │   └── production/
│   ├── main.tf
│   ├── variables.tf
│   └── outputs.tf
│
├── helm/                      # Helm charts (if applicable)
│   └── [project-name]/
│       ├── Chart.yaml
│       ├── values.yaml
│       ├── values-dev.yaml
│       ├── values-prod.yaml
│       └── templates/
│
└── README.md                  # Infrastructure documentation
```

**Organization Principles**:
- **Separation by Tool**: Docker, K8s, Terraform in separate folders
- **Environment Isolation**: Separate configs for dev/staging/prod
- **Reusability**: Shared modules and templates
- **Documentation**: README in each major folder

---

## Root-Level Configuration Files

### `.editorconfig`

**Purpose**: Consistent code formatting across editors and IDEs

**Content**: Character encoding, indent style, line endings

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
```

---

### `.gitignore`

**Purpose**: Prevent committing build artifacts, dependencies, secrets

**Key Sections**:
- Build outputs (bin/, obj/, dist/, build/)
- Dependencies (node_modules/, packages/)
- IDE files (.vs/, .vscode/, .idea/)
- Environment files (.env, *.env)
- OS files (.DS_Store, Thumbs.db)

---

### `.env.example`

**Purpose**: Template for required environment variables

**Usage**: Copy to `.env` and fill in actual values

```bash
# Database
DATABASE_HOST=localhost
DATABASE_PORT=5432
DATABASE_NAME=projectdb
DATABASE_USER=postgres
DATABASE_PASSWORD=changeme

# Application
API_BASE_URL=http://localhost:5000
FRONTEND_URL=http://localhost:3000

# JWT
JWT_SECRET_KEY=your-secret-key-min-32-chars
JWT_EXPIRATION_HOURS=24

# External Services
SMTP_HOST=smtp.example.com
SMTP_PORT=587
SMTP_USER=noreply@example.com
SMTP_PASSWORD=changeme
```

---

### `docker-compose.yml`

**Purpose**: Local development environment orchestration

**Defines**: Database, cache, backend, frontend services

**Location**: Project root (for easy `docker-compose up`)

---

### `README.md`

**Purpose**: Project overview, quick start, essential links

**Sections**:
- Project description
- Quick start (< 5 minutes)
- Prerequisites
- Development setup
- Testing
- Deployment
- Documentation links
- Contributing

---

### `CONTRIBUTING.md`

**Purpose**: Guidelines for contributing to the project

**Sections**:
- Code of conduct
- Development workflow
- Branch naming
- Commit message format
- Pull request process
- Code standards
- Testing requirements

---

### `LICENSE`

**Purpose**: Project license (MIT, Apache, proprietary, etc.)

**Location**: Project root

---

## File Naming Conventions

### C# Backend

- **Classes**: PascalCase - `UserService.cs`
- **Interfaces**: PascalCase with 'I' prefix - `IUserRepository.cs`
- **Enums**: PascalCase - `OrderStatus.cs`
- **Constants**: PascalCase - `AppConstants.cs`
- **Tests**: PascalCase with 'Tests' suffix - `UserServiceTests.cs`

### TypeScript/React Frontend

- **Components**: PascalCase - `UserCard.tsx`
- **Hooks**: camelCase with 'use' prefix - `useAuth.ts`
- **Services**: camelCase with 'Service' suffix - `userService.ts`
- **Utilities**: camelCase - `formatters.ts`
- **Types**: camelCase with '.types' suffix - `user.types.ts`
- **Tests**: Same as file with '.test' suffix - `UserCard.test.tsx`

### General

- **Configuration**: kebab-case - `docker-compose.yml`
- **Scripts**: kebab-case - `setup-dev.sh`
- **Markdown**: kebab-case - `getting-started.md`
- **Directories**: kebab-case - `user-management/`

---

## Organization Principles

### 1. Separation of Concerns

- **Presentation Layer** (API/Controllers): HTTP concerns only
- **Domain Layer** (Core): Business logic and rules
- **Infrastructure Layer**: External dependencies (database, services)
- **Test Layer**: Separate from production code

### 2. Feature-Based Organization

Group related files together by feature/domain:
- Better than purely layer-based organization
- Easier to understand and maintain
- Supports independent development

### 3. Explicit Dependencies

- Dependencies flow inward (Infrastructure → Core ← API)
- Core has no dependencies on outer layers
- Use interfaces to invert dependencies

### 4. Testability

- Structure supports easy mocking
- Test files mirror source structure
- Shared test utilities in fixtures

### 5. Scalability

- Structure supports adding new features
- Clear boundaries between components
- Easy to split into microservices later

---

## Technology-Specific Variations

### Python (Django/Flask) Backend

```
src/backend/
├── app/
│   ├── __init__.py
│   ├── models/
│   ├── views/
│   ├── serializers/
│   └── urls.py
├── config/
│   ├── settings.py
│   └── urls.py
├── requirements.txt
└── manage.py
```

### Node.js (Express) Backend

```
src/backend/
├── src/
│   ├── controllers/
│   ├── models/
│   ├── routes/
│   ├── middleware/
│   └── app.ts
├── package.json
├── tsconfig.json
└── server.ts
```

### Vue.js Frontend

```
src/frontend/
├── src/
│   ├── components/
│   ├── views/
│   ├── router/
│   ├── store/
│   └── App.vue
└── package.json
```

---

## Common Anti-Patterns to Avoid

### ❌ Deep Nesting

```
Bad:
src/backend/Api/Controllers/V1/Admin/Users/Management/UserController.cs

Good:
src/backend/Api/Controllers/Admin/UsersController.cs
```

### ❌ Mixed Concerns

```
Bad:
src/backend/Api/UserControllerWithRepositoryAndBusinessLogic.cs

Good:
src/backend/Api/Controllers/UserController.cs
src/backend/Core/Services/UserService.cs
src/backend/Infrastructure/Repositories/UserRepository.cs
```

### ❌ Unclear Naming

```
Bad:
src/frontend/src/components/Comp1.tsx
src/frontend/src/utils/helpers.ts

Good:
src/frontend/src/components/UserCard.tsx
src/frontend/src/utils/dateFormatters.ts
```

### ❌ No Organization

```
Bad:
src/
├── file1.cs
├── file2.cs
├── file3.tsx
├── file4.ts
└── ... (100 files in root)

Good:
src/
├── backend/ (organized by layer)
└── frontend/ (organized by feature)
```

---

## Validation Checklist

Use this checklist to validate repository structure:

- [ ] Directory structure matches template for technology stack
- [ ] All configuration files in correct locations
- [ ] Naming conventions followed consistently
- [ ] No deep nesting (max 4-5 levels)
- [ ] Clear separation of concerns (layers/features)
- [ ] Test structure mirrors source structure
- [ ] Documentation organized logically
- [ ] Scripts are executable and documented
- [ ] No mixed concerns in single file
- [ ] README.md provides clear overview
- [ ] .gitignore prevents committing artifacts
- [ ] .env.example lists all required variables

---

## Maintenance

### When to Update This Document

- New major directory added
- Technology stack changes
- Organization principle changes
- Team agrees on new conventions

### Version History

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | [Date] | Initial structure created | [Name] |

---

## References

- [Clean Architecture](https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html)
- [Project Structure Best Practices](https://docs.microsoft.com/en-us/dotnet/architecture/)
- [React File Structure](https://reactjs.org/docs/faq-structure.html)

---

*This repository structure document is the authoritative reference for project organization. All code must follow this structure.*
