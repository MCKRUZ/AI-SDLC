# Repository Structure

**Project Name**: [Project name from constitution]  
**Date Created**: [YYYY-MM-DD]  
**Last Updated**: [YYYY-MM-DD]  
**Repository URL**: [Git repository URL]  
**Architecture**: [Monorepo / Multi-repo / Hybrid]

---

## Purpose of This Document

This document defines the **standard repository structure and organization** for the project, ensuring consistency, maintainability, and discoverability across the codebase.

**What This Document Contains**:
- Complete directory structure
- Naming conventions
- File organization principles
- Configuration file locations
- Documentation structure
- Build and deployment artifacts

**What This Document Does NOT Contain**:
- Code implementation details
- Detailed build instructions (see README)
- API documentation (see generated docs)

**Who Uses This Document**:
- Developers: Navigate and organize code
- DevOps: Understand deployment structure
- New team members: Onboarding reference
- Technical leads: Enforce standards

---

## Repository Overview

### Repository Type

**[Select one and expand]**:

#### Option A: Monorepo
Single repository containing all code (frontend, backend, shared libraries).

**Pros**: Simplified dependency management, atomic changes across components, easier refactoring  
**Cons**: Larger repository, potential build complexity  
**Best for**: Small to medium projects, tightly coupled components

#### Option B: Multi-repo
Separate repositories for frontend, backend, and shared components.

**Pros**: Independent deployment, clear boundaries, smaller repos  
**Cons**: Dependency management across repos, versioning complexity  
**Best for**: Large projects, microservices, independent teams

#### Option C: Hybrid
Monorepo for application code, separate repos for infrastructure and shared libraries.

**Pros**: Balance of monorepo benefits with some separation  
**Cons**: Some complexity of both approaches  
**Best for**: Medium to large projects with distinct components

---

## Directory Structure

### Monorepo Structure (Full Example)

```
project-root/
├── .github/                          # GitHub-specific files
│   ├── workflows/                    # GitHub Actions CI/CD
│   │   ├── ci.yml                   # Continuous Integration
│   │   ├── cd-staging.yml           # Deploy to staging
│   │   ├── cd-production.yml        # Deploy to production
│   │   └── security-scan.yml        # Security scanning
│   ├── ISSUE_TEMPLATE/              # Issue templates
│   │   ├── bug_report.md
│   │   ├── feature_request.md
│   │   └── task.md
│   ├── PULL_REQUEST_TEMPLATE.md     # PR template
│   └── CODEOWNERS                    # Code ownership rules
│
├── docs/                             # Project documentation
│   ├── architecture/                 # Architecture docs
│   │   ├── architecture.md          # System architecture
│   │   ├── adr/                     # Architecture Decision Records
│   │   │   ├── 0001-use-microservices.md
│   │   │   ├── 0002-choose-react.md
│   │   │   └── 0003-database-choice.md
│   │   ├── diagrams/                # Architecture diagrams
│   │   │   ├── system-context.puml
│   │   │   ├── container-diagram.puml
│   │   │   └── deployment-diagram.puml
│   │   └── data-model.md            # Database schema docs
│   ├── api/                         # API documentation
│   │   ├── openapi.yaml             # OpenAPI/Swagger spec
│   │   └── postman-collection.json  # Postman API collection
│   ├── development/                 # Development guides
│   │   ├── setup.md                 # Development setup
│   │   ├── coding-standards.md      # Code style guide
│   │   ├── testing-guide.md         # Testing practices
│   │   └── deployment-guide.md      # Deployment instructions
│   ├── user/                        # User documentation
│   │   ├── user-guide.md           # End user guide
│   │   └── faq.md                  # Frequently asked questions
│   └── runbooks/                    # Operational runbooks
│       ├── incident-response.md
│       ├── deployment.md
│       └── monitoring.md
│
├── src/                             # Source code
│   ├── backend/                     # Backend application
│   │   ├── src/                     # Backend source
│   │   │   ├── Api/                # API layer
│   │   │   │   ├── Controllers/    # API controllers
│   │   │   │   │   ├── AuthController.cs
│   │   │   │   │   ├── UsersController.cs
│   │   │   │   │   └── ProductsController.cs
│   │   │   │   ├── Middleware/     # Custom middleware
│   │   │   │   │   ├── AuthenticationMiddleware.cs
│   │   │   │   │   ├── ErrorHandlingMiddleware.cs
│   │   │   │   │   └── LoggingMiddleware.cs
│   │   │   │   ├── Filters/        # Action filters
│   │   │   │   ├── Models/         # Request/Response DTOs
│   │   │   │   │   ├── Requests/
│   │   │   │   │   └── Responses/
│   │   │   │   └── Program.cs      # Application entry point
│   │   │   ├── Core/               # Business logic layer
│   │   │   │   ├── Domain/         # Domain entities
│   │   │   │   │   ├── Entities/
│   │   │   │   │   │   ├── User.cs
│   │   │   │   │   │   ├── Product.cs
│   │   │   │   │   │   └── Order.cs
│   │   │   │   │   ├── ValueObjects/ # Domain value objects
│   │   │   │   │   └── Enums/      # Domain enumerations
│   │   │   │   ├── Interfaces/     # Core interfaces
│   │   │   │   │   ├── IRepository.cs
│   │   │   │   │   ├── IUserService.cs
│   │   │   │   │   └── IEmailService.cs
│   │   │   │   ├── Services/       # Business services
│   │   │   │   │   ├── UserService.cs
│   │   │   │   │   ├── ProductService.cs
│   │   │   │   │   └── OrderService.cs
│   │   │   │   ├── Validators/     # Business rule validators
│   │   │   │   ├── Exceptions/     # Custom exceptions
│   │   │   │   └── Constants/      # Business constants
│   │   │   ├── Infrastructure/     # Infrastructure layer
│   │   │   │   ├── Data/           # Data access
│   │   │   │   │   ├── Context/
│   │   │   │   │   │   └── ApplicationDbContext.cs
│   │   │   │   │   ├── Repositories/
│   │   │   │   │   │   ├── UserRepository.cs
│   │   │   │   │   │   ├── ProductRepository.cs
│   │   │   │   │   │   └── OrderRepository.cs
│   │   │   │   │   ├── Configurations/ # EF configurations
│   │   │   │   │   └── Migrations/  # Database migrations
│   │   │   │   ├── ExternalServices/ # Third-party integrations
│   │   │   │   │   ├── EmailService.cs
│   │   │   │   │   ├── PaymentService.cs
│   │   │   │   │   └── SmsService.cs
│   │   │   │   ├── Caching/        # Cache implementations
│   │   │   │   ├── Logging/        # Logging implementations
│   │   │   │   └── Security/       # Security implementations
│   │   │   └── Shared/             # Shared utilities
│   │   │       ├── Extensions/     # Extension methods
│   │   │       ├── Helpers/        # Helper classes
│   │   │       └── Utils/          # Utility functions
│   │   ├── tests/                  # Backend tests
│   │   │   ├── UnitTests/         # Unit tests
│   │   │   │   ├── Services/      # Service tests
│   │   │   │   ├── Validators/    # Validator tests
│   │   │   │   └── Utilities/     # Utility tests
│   │   │   ├── IntegrationTests/  # Integration tests
│   │   │   │   ├── Api/           # API integration tests
│   │   │   │   ├── Data/          # Database tests
│   │   │   │   └── ExternalServices/ # External service tests
│   │   │   └── TestUtilities/     # Test helpers
│   │   │       ├── Fixtures/      # Test fixtures
│   │   │       ├── Mocks/         # Mock objects
│   │   │       └── Builders/      # Test data builders
│   │   ├── Backend.Api.csproj     # API project file
│   │   ├── Backend.Core.csproj    # Core project file
│   │   ├── Backend.Infrastructure.csproj
│   │   └── Backend.sln            # Solution file
│   │
│   ├── frontend/                   # Frontend application
│   │   ├── public/                # Static assets
│   │   │   ├── index.html         # HTML entry point
│   │   │   ├── favicon.ico        # Favicon
│   │   │   ├── manifest.json      # PWA manifest
│   │   │   └── robots.txt         # Robots.txt
│   │   ├── src/                   # Frontend source
│   │   │   ├── app/               # Application root
│   │   │   │   ├── App.tsx        # Root component
│   │   │   │   ├── App.test.tsx   # Root tests
│   │   │   │   └── App.css        # Root styles
│   │   │   ├── components/        # Reusable components
│   │   │   │   ├── common/        # Common components
│   │   │   │   │   ├── Button/
│   │   │   │   │   │   ├── Button.tsx
│   │   │   │   │   │   ├── Button.test.tsx
│   │   │   │   │   │   └── Button.module.css
│   │   │   │   │   ├── Input/
│   │   │   │   │   ├── Modal/
│   │   │   │   │   └── Card/
│   │   │   │   ├── layout/        # Layout components
│   │   │   │   │   ├── Header/
│   │   │   │   │   ├── Footer/
│   │   │   │   │   ├── Sidebar/
│   │   │   │   │   └── Navigation/
│   │   │   │   └── forms/         # Form components
│   │   │   │       ├── LoginForm/
│   │   │   │       ├── RegisterForm/
│   │   │   │       └── ProfileForm/
│   │   │   ├── pages/             # Page components
│   │   │   │   ├── Home/
│   │   │   │   │   ├── HomePage.tsx
│   │   │   │   │   ├── HomePage.test.tsx
│   │   │   │   │   └── HomePage.module.css
│   │   │   │   ├── Auth/
│   │   │   │   │   ├── LoginPage.tsx
│   │   │   │   │   └── RegisterPage.tsx
│   │   │   │   ├── Products/
│   │   │   │   │   ├── ProductListPage.tsx
│   │   │   │   │   └── ProductDetailPage.tsx
│   │   │   │   └── Profile/
│   │   │   ├── features/          # Feature modules
│   │   │   │   ├── auth/          # Authentication feature
│   │   │   │   │   ├── services/  # Auth services
│   │   │   │   │   ├── hooks/     # Auth hooks
│   │   │   │   │   └── types/     # Auth types
│   │   │   │   ├── products/      # Products feature
│   │   │   │   └── orders/        # Orders feature
│   │   │   ├── services/          # Shared services
│   │   │   │   ├── api/           # API client
│   │   │   │   │   ├── apiClient.ts
│   │   │   │   │   ├── authApi.ts
│   │   │   │   │   ├── usersApi.ts
│   │   │   │   │   └── productsApi.ts
│   │   │   │   ├── storage/       # Local storage
│   │   │   │   └── analytics/     # Analytics tracking
│   │   │   ├── store/             # State management
│   │   │   │   ├── slices/        # Redux slices
│   │   │   │   │   ├── authSlice.ts
│   │   │   │   │   ├── userSlice.ts
│   │   │   │   │   └── productsSlice.ts
│   │   │   │   └── store.ts       # Store configuration
│   │   │   ├── hooks/             # Custom React hooks
│   │   │   │   ├── useAuth.ts
│   │   │   │   ├── useApi.ts
│   │   │   │   └── useDebounce.ts
│   │   │   ├── utils/             # Utility functions
│   │   │   │   ├── validators.ts
│   │   │   │   ├── formatters.ts
│   │   │   │   └── helpers.ts
│   │   │   ├── types/             # TypeScript types
│   │   │   │   ├── user.types.ts
│   │   │   │   ├── product.types.ts
│   │   │   │   └── api.types.ts
│   │   │   ├── constants/         # Constants
│   │   │   │   ├── routes.ts
│   │   │   │   └── config.ts
│   │   │   ├── styles/            # Global styles
│   │   │   │   ├── variables.css  # CSS variables
│   │   │   │   ├── globals.css    # Global styles
│   │   │   │   └── theme.ts       # Theme configuration
│   │   │   ├── assets/            # Images, fonts, etc.
│   │   │   │   ├── images/
│   │   │   │   ├── fonts/
│   │   │   │   └── icons/
│   │   │   └── index.tsx          # Application entry
│   │   ├── tests/                 # Frontend tests
│   │   │   ├── unit/             # Unit tests
│   │   │   ├── integration/      # Integration tests
│   │   │   ├── e2e/              # E2E tests
│   │   │   └── __mocks__/        # Mock data
│   │   ├── package.json          # NPM dependencies
│   │   ├── tsconfig.json         # TypeScript config
│   │   ├── vite.config.ts        # Vite configuration
│   │   ├── .eslintrc.js          # ESLint configuration
│   │   └── .prettierrc           # Prettier configuration
│   │
│   └── shared/                    # Shared code (if monorepo)
│       ├── types/                 # Shared TypeScript types
│       ├── constants/             # Shared constants
│       └── utils/                 # Shared utilities
│
├── infrastructure/                # Infrastructure as Code
│   ├── terraform/                # Terraform configurations
│   │   ├── environments/         # Environment-specific configs
│   │   │   ├── dev/
│   │   │   ├── staging/
│   │   │   └── production/
│   │   ├── modules/              # Reusable Terraform modules
│   │   │   ├── vpc/
│   │   │   ├── database/
│   │   │   ├── compute/
│   │   │   └── storage/
│   │   └── main.tf              # Main Terraform file
│   ├── kubernetes/              # Kubernetes manifests
│   │   ├── base/                # Base configurations
│   │   ├── overlays/            # Environment overlays
│   │   │   ├── dev/
│   │   │   ├── staging/
│   │   │   └── production/
│   │   └── helm/                # Helm charts
│   ├── docker/                  # Docker configurations
│   │   ├── backend/
│   │   │   └── Dockerfile
│   │   ├── frontend/
│   │   │   └── Dockerfile
│   │   └── docker-compose.yml   # Local development
│   └── scripts/                 # Infrastructure scripts
│       ├── setup.sh            # Initial setup
│       ├── deploy.sh           # Deployment script
│       └── backup.sh           # Backup script
│
├── database/                    # Database files
│   ├── migrations/             # Database migrations
│   │   ├── V001__Initial_Schema.sql
│   │   ├── V002__Add_Products_Table.sql
│   │   └── V003__Add_Orders_Table.sql
│   ├── seeds/                  # Seed data scripts
│   │   ├── 001_seed_users.sql
│   │   └── 002_seed_products.sql
│   └── scripts/                # Database utility scripts
│       ├── backup.sh
│       └── restore.sh
│
├── scripts/                     # Project scripts
│   ├── setup.sh                # Initial project setup
│   ├── test.sh                 # Run all tests
│   ├── lint.sh                 # Run linters
│   ├── deploy.sh               # Deployment script
│   └── generate-docs.sh        # Generate documentation
│
├── tools/                       # Development tools
│   ├── generators/             # Code generators
│   ├── analyzers/              # Code analyzers
│   └── validators/             # Validation tools
│
├── config/                      # Configuration files
│   ├── development.json        # Dev configuration
│   ├── staging.json           # Staging configuration
│   ├── production.json        # Production configuration
│   └── .env.example           # Environment variables template
│
├── .vscode/                     # VS Code settings
│   ├── settings.json          # Editor settings
│   ├── extensions.json        # Recommended extensions
│   ├── launch.json            # Debug configurations
│   └── tasks.json             # Task configurations
│
├── .editorconfig               # Editor configuration
├── .gitignore                  # Git ignore rules
├── .gitattributes             # Git attributes
├── README.md                   # Project README
├── CONTRIBUTING.md            # Contribution guidelines
├── LICENSE                     # License file
└── CHANGELOG.md               # Change log

```

---

## Naming Conventions

### General Principles

1. **Be Descriptive**: Names should clearly indicate purpose
2. **Be Consistent**: Follow established patterns
3. **Be Concise**: Avoid unnecessarily long names
4. **Use Standard Casing**: Follow language conventions

### File Naming

**Backend (C#)**:
- PascalCase for files: `UserController.cs`, `ProductService.cs`
- Interfaces prefixed with I: `IUserRepository.cs`
- Tests suffixed with Tests: `UserServiceTests.cs`

**Frontend (TypeScript/React)**:
- PascalCase for components: `UserProfile.tsx`, `ProductCard.tsx`
- camelCase for utilities: `apiClient.ts`, `validators.ts`
- kebab-case for CSS modules: `user-profile.module.css`
- Tests colocated with source: `UserProfile.test.tsx`

**Infrastructure**:
- kebab-case for configs: `deployment-config.yaml`
- Descriptive names: `vpc-network.tf`, `database-instance.tf`

### Directory Naming

- **lowercase with hyphens**: `user-management/`, `api-controllers/`
- **Plural for collections**: `controllers/`, `services/`, `models/`
- **Singular for single purpose**: `config/`, `middleware/`

### Variable Naming

**Backend (C#)**:
- PascalCase for public: `public string UserName { get; set; }`
- camelCase for private: `private string userName;`
- UPPER_CASE for constants: `public const int MAX_RETRY_COUNT = 3;`

**Frontend (TypeScript)**:
- camelCase for variables: `const userName = "John";`
- PascalCase for types/interfaces: `interface UserProfile { }`
- UPPER_CASE for constants: `const API_BASE_URL = "...";`

---

## Configuration Management

### Environment Variables

**Location**: Root directory `.env` files (never commit with secrets!)

**Pattern**:
```
# .env.example (commit this)
DATABASE_URL=postgresql://localhost:5432/myapp
API_KEY=your_api_key_here
JWT_SECRET=your_secret_here

# .env.development (local only)
DATABASE_URL=postgresql://localhost:5432/myapp_dev
API_KEY=dev_api_key
JWT_SECRET=dev_secret

# .env.production (managed by deployment system)
# DO NOT COMMIT THIS FILE
```

**Best Practices**:
- Always have `.env.example` in version control
- Never commit actual `.env` files with secrets
- Use different values for each environment
- Document all required environment variables

### Configuration Files

**Backend Configuration** (`appsettings.json`):
```json
{
  "Logging": {
    "LogLevel": {
      "Default": "Information"
    }
  },
  "ConnectionStrings": {
    "DefaultConnection": "..."
  },
  "JwtSettings": {
    "SecretKey": "...",
    "Issuer": "...",
    "Audience": "..."
  }
}
```

**Frontend Configuration** (environment-based):
```typescript
// src/config/config.ts
export const config = {
  apiBaseUrl: process.env.VITE_API_BASE_URL,
  environment: process.env.VITE_ENVIRONMENT,
  features: {
    enableAnalytics: process.env.VITE_ENABLE_ANALYTICS === 'true'
  }
};
```

---

## Documentation Structure

### Code Documentation

**Backend (C#)**: XML documentation comments
```csharp
/// <summary>
/// Registers a new user in the system
/// </summary>
/// <param name="userData">User registration data</param>
/// <returns>Created user with ID</returns>
/// <exception cref="ValidationException">If user data is invalid</exception>
public async Task<User> RegisterUser(UserRegistration userData)
{
    // Implementation
}
```

**Frontend (TypeScript)**: JSDoc comments
```typescript
/**
 * Validates user email format
 * @param email - Email address to validate
 * @returns True if email is valid, false otherwise
 * @example
 * validateEmail("user@example.com") // returns true
 * validateEmail("invalid") // returns false
 */
export function validateEmail(email: string): boolean {
    // Implementation
}
```

### README Files

**Root README.md** (comprehensive):
- Project overview
- Prerequisites
- Installation instructions
- Running the application
- Testing
- Deployment
- Contributing guidelines
- License information

**Component READMEs** (specific):
- Backend: `src/backend/README.md`
- Frontend: `src/frontend/README.md`
- Infrastructure: `infrastructure/README.md`

---

## Build and Deployment Artifacts

### Build Outputs

**Backend**:
- Location: `src/backend/bin/`
- Gitignore: Yes
- Contains: Compiled DLLs, executables

**Frontend**:
- Location: `src/frontend/dist/` or `src/frontend/build/`
- Gitignore: Yes
- Contains: Bundled JavaScript, CSS, HTML

### Deployment Artifacts

**Docker Images**:
- Built by CI/CD
- Tagged with version and commit SHA
- Pushed to container registry

**Database Migrations**:
- Location: `database/migrations/`
- Version controlled
- Applied during deployment

---

## Version Control Strategy

### Branching Strategy

**Main Branches**:
- `main`: Production-ready code
- `develop`: Integration branch for features

**Supporting Branches**:
- `feature/*`: New features (`feature/user-authentication`)
- `bugfix/*`: Bug fixes (`bugfix/login-error`)
- `hotfix/*`: Production hotfixes (`hotfix/security-patch`)
- `release/*`: Release preparation (`release/v1.2.0`)

### Commit Messages

**Format**:
```
<type>(<scope>): <subject>

<body>

<footer>
```

**Types**:
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation only
- `style`: Code formatting
- `refactor`: Code restructuring
- `test`: Adding tests
- `chore`: Maintenance tasks

**Example**:
```
feat(auth): add JWT token refresh functionality

Implement automatic token refresh when token expires.
Includes refresh token storage and rotation.

Closes #123
```

### .gitignore Essentials

```gitignore
# Dependencies
node_modules/
vendor/

# Build outputs
dist/
build/
bin/
obj/

# Environment variables
.env
.env.local
.env.*.local

# IDE files
.vscode/
.idea/
*.suo
*.user

# OS files
.DS_Store
Thumbs.db

# Logs
*.log
logs/

# Test coverage
coverage/
*.coverage

# Temporary files
*.tmp
*.temp
```

---

## Testing Structure

### Test Organization

**Backend Tests**:
```
tests/
├── UnitTests/          # Fast, isolated tests
│   ├── Services/
│   ├── Validators/
│   └── Utilities/
├── IntegrationTests/   # Tests with dependencies
│   ├── Api/
│   ├── Database/
│   └── ExternalServices/
└── TestUtilities/      # Shared test helpers
    ├── Fixtures/
    ├── Mocks/
    └── Builders/
```

**Frontend Tests**:
```
tests/
├── unit/              # Component unit tests
├── integration/       # Integration tests
├── e2e/              # End-to-end tests
│   ├── specs/
│   └── fixtures/
└── __mocks__/        # Mock data and modules
```

### Test File Naming

**Backend**: `{ClassName}Tests.cs`
- Example: `UserServiceTests.cs`

**Frontend**: `{ComponentName}.test.tsx`
- Example: `UserProfile.test.tsx`

---

## Security Considerations

### Secrets Management

**Never Commit**:
- API keys
- Database passwords
- JWT secrets
- SSL certificates
- Private keys

**Use Instead**:
- Environment variables
- Secret management services (Azure Key Vault, AWS Secrets Manager)
- Encrypted configuration files (with keys stored separately)

### File Permissions

**Sensitive Files**:
- `.env` files: 600 (read/write owner only)
- Private keys: 600
- Config files with secrets: 640

---

## Monorepo vs Multi-repo Guidance

### Choose Monorepo If:
- Tightly coupled components
- Atomic changes across components needed
- Small to medium team
- Want simplified dependency management

### Choose Multi-repo If:
- Loosely coupled services
- Independent deployment schedules
- Large team with clear boundaries
- Different tech stacks per component

### Monorepo Tools:
- **Nx**: Advanced build system
- **Turborepo**: High-performance build system
- **Lerna**: JavaScript monorepo management
- **Yarn Workspaces**: Package management
- **npm Workspaces**: Package management

---

## Development Workflow Integration

### IDE Configuration

**VS Code** (`.vscode/`):
- `settings.json`: Editor preferences
- `extensions.json`: Recommended extensions
- `launch.json`: Debug configurations
- `tasks.json`: Build and run tasks

**Example `.vscode/settings.json`**:
```json
{
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  },
  "typescript.tsdk": "node_modules/typescript/lib",
  "files.exclude": {
    "**/node_modules": true,
    "**/dist": true
  }
}
```

### EditorConfig

**`.editorconfig`** (language-agnostic editor config):
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
```

---

## Migration Path

### From Existing Codebase

If migrating from existing structure:

1. **Create new structure in parallel**
2. **Move files incrementally**
3. **Update imports/references**
4. **Test thoroughly after each move**
5. **Delete old structure when complete**

### Gradual Adoption

- Start with new projects/features
- Refactor existing code over time
- Update documentation as you go
- Don't try to change everything at once

---

## Maintenance

### Regular Reviews

**Monthly**:
- Review unused dependencies
- Check for outdated packages
- Audit file organization
- Remove dead code

**Quarterly**:
- Major dependency updates
- Structure improvements
- Documentation updates
- Archive old branches

### Cleanup Scripts

**Remove build artifacts**:
```bash
#!/bin/bash
# scripts/clean.sh
rm -rf src/backend/bin
rm -rf src/backend/obj
rm -rf src/frontend/dist
rm -rf src/frontend/node_modules
```

**Find unused files**:
```bash
#!/bin/bash
# scripts/find-unused.sh
# Use tools like depcheck, webpack-unused, etc.
```

---

## Best Practices

### DO:
- ✅ Keep structure flat (avoid deep nesting)
- ✅ Group by feature, not file type
- ✅ Colocate related files (tests with source)
- ✅ Use consistent naming
- ✅ Document structure decisions
- ✅ Keep README files updated
- ✅ Use .gitignore properly

### DON'T:
- ❌ Create "utils" or "helpers" dumping grounds
- ❌ Mix concerns (UI logic in API controllers)
- ❌ Commit build artifacts
- ❌ Commit secrets or credentials
- ❌ Create deeply nested structures
- ❌ Use inconsistent naming
- ❌ Leave outdated documentation

---

## Change Log

| Version | Date | Changed By | Changes | Reason |
|---------|------|------------|---------|---------|
| v1.0 | [Date] | [Name] | Initial repository structure | Project setup |

---

## Notes

This structure is a **starting point**, not a rigid requirement. Adapt it based on:
- Project size and complexity
- Team size and structure
- Technology choices
- Deployment requirements
- Organizational standards

**Remember: Good structure makes code discoverable, maintainable, and scalable. Invest time in structure early to save time later.**
