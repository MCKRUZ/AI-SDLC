# Repository Patterns Reference

## Overview

Good repository structure enables efficient development, clear ownership,
and effective collaboration.

---

## Repository Strategies

### Monorepo

All code in one repository.

```
company-monorepo/
├── apps/
│   ├── web/
│   ├── mobile/
│   └── api/
├── packages/
│   ├── shared-ui/
│   ├── utils/
│   └── types/
└── tools/
```

| Pros | Cons |
|------|------|
| Single source of truth | Large clone size |
| Easy cross-project changes | Complex CI/CD |
| Shared tooling | Ownership can be unclear |

**Best for**: Tightly coupled services, shared components

### Multi-repo (Polyrepo)

Each service/component in its own repository.

```
company-org/
├── web-app/
├── mobile-app/
├── api-service/
├── auth-service/
└── shared-utils/
```

| Pros | Cons |
|------|------|
| Clear ownership | Cross-repo changes harder |
| Independent deployments | Dependency management |
| Smaller, focused repos | Duplication risk |

**Best for**: Independent teams, microservices

---

## Folder Structure

### Web Application (React/Next.js)

```
src/
├── app/                 # Next.js app router pages
├── components/
│   ├── ui/             # Reusable UI components
│   └── features/       # Feature-specific components
├── hooks/              # Custom React hooks
├── lib/                # Utility functions
├── services/           # API clients, external services
├── stores/             # State management
├── types/              # TypeScript definitions
└── styles/             # Global styles
```

### API Service (Node.js)

```
src/
├── controllers/        # Request handlers
├── services/           # Business logic
├── models/             # Data models
├── repositories/       # Data access
├── middleware/         # Express middleware
├── routes/             # Route definitions
├── utils/              # Helpers
├── types/              # TypeScript definitions
└── config/             # Configuration
```

### .NET API

```
src/
├── Api/                # Controllers, DTOs
├── Application/        # Use cases, services
├── Domain/             # Entities, value objects
├── Infrastructure/     # Data access, external services
└── Shared/             # Common utilities
tests/
├── Api.Tests/
├── Application.Tests/
└── Integration.Tests/
```

---

## Branching Strategies

### Git Flow

```
main (production)
  └── develop
        ├── feature/user-auth
        ├── feature/checkout
        └── release/v1.2
              └── hotfix/critical-bug
```

| Branch | Purpose |
|--------|---------|
| main | Production code |
| develop | Integration branch |
| feature/* | New features |
| release/* | Release preparation |
| hotfix/* | Production fixes |

### Trunk-Based Development

```
main (trunk)
  ├── feature/user-auth (short-lived)
  └── feature/checkout (short-lived)
```

| Pros | Cons |
|------|------|
| Simpler | Requires feature flags |
| Faster integration | Needs strong CI/CD |
| Less merge conflicts | May need more discipline |

---

## Essential Files

### Root Level

```
.
├── README.md           # Project overview, setup
├── CONTRIBUTING.md     # How to contribute
├── CHANGELOG.md        # Version history
├── LICENSE             # License terms
├── .gitignore          # Ignored files
├── .editorconfig       # Editor settings
└── .env.example        # Environment template
```

### Configuration Files

```
.
├── package.json        # Node.js dependencies
├── tsconfig.json       # TypeScript config
├── .eslintrc.js        # Linting rules
├── .prettierrc         # Formatting rules
├── jest.config.js      # Test configuration
└── docker-compose.yml  # Local development
```

### CI/CD

```
.github/
├── workflows/
│   ├── ci.yml          # Build & test
│   ├── cd.yml          # Deploy
│   └── pr.yml          # PR checks
├── CODEOWNERS          # Review assignments
└── pull_request_template.md
```

---

## Code Ownership

### CODEOWNERS File

```
# Default owners
* @team-lead

# Frontend
/src/components/ @frontend-team
/src/styles/ @frontend-team

# Backend
/src/api/ @backend-team
/src/services/ @backend-team

# Infrastructure
/infra/ @devops-team
/.github/ @devops-team
```

---

## README Template

```markdown
# Project Name

Brief description of what this project does.

## Quick Start

\`\`\`bash
git clone <repo>
cd <project>
npm install
npm run dev
\`\`\`

## Prerequisites

- Node.js 18+
- Docker

## Development

[Development workflow instructions]

## Testing

\`\`\`bash
npm test
\`\`\`

## Deployment

[Deployment instructions]

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md)
```

---

## Quick Reference

**New project checklist**:
- [ ] README with setup instructions
- [ ] CONTRIBUTING guide
- [ ] .gitignore properly configured
- [ ] CI/CD pipeline
- [ ] CODEOWNERS defined
- [ ] Branch protection rules
- [ ] Environment variable template
