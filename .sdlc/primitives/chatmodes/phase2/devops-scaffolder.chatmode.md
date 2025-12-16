# DevOps Scaffolder Chatmode

## Purpose
Focused infrastructure setup, repository scaffolding, and CI/CD pipeline sessions using the DevOps Scaffolder Agent.

## When to Use This Mode
- Setting up repository structure
- Creating CI/CD pipelines
- Configuring development environments
- Setting up containerization (Docker)
- Configuring cloud infrastructure
- Creating developer onboarding documentation
- Setting up monitoring and observability

## Session Setup

### Before Starting
Load these artifacts into context:
1. DevOps Scaffolder instructions (`devops-scaffolder_instructions.md`)
2. Phase 2 config (`../../config/phase2_config.md`)
3. From Phase 1:
   - Architecture (`phase1/artifacts/architecture.md`)
   - Constitution (`phase1/artifacts/constitution.md`) - quality standards
   - Data Model (`phase1/artifacts/data-model.md`) - for database setup
4. Technical stack context (`../../memory/technical-stack_context.md`)
5. Organization context (`../../memory/organization_context.md`)
6. Repository structure template (`../templates/phase2/repository-structure_template.md`)
7. Environment config template (`../templates/phase2/environment-config_template.md`)

### Agent Instructions
Load: `devops-scaffolder_instructions.md`

### Session Goal
Define a clear goal for the session:
- "Create repository structure for [project]"
- "Set up CI/CD pipeline"
- "Configure development environment"
- "Create Docker configuration"
- "Set up cloud infrastructure"
- "Create developer onboarding guide"

---

## Interaction Patterns

### Pattern 1: Repository Structure Setup

**When to Use**: Creating the initial repository structure

**Opening Prompt**:
```
I need to set up the repository structure for [project].

Architecture Summary:
[Paste relevant architecture sections - especially component structure]

Tech Stack:
- Languages: [List]
- Frameworks: [List]
- Database: [Type]
- Cloud: [Provider if known]

Team Preferences:
- Monorepo or multi-repo: [Preference]
- Branching strategy: [GitFlow / Trunk-based / etc.]
- Code review requirements: [From constitution]

Please create a repository structure including:
1. Directory layout
2. README.md structure
3. .gitignore configuration
4. Branch protection rules
5. PR template
6. Issue templates
7. CODEOWNERS if applicable
```

**Follow-up for Specific Directories**:
```
Let's detail the [src/tests/docs/etc.] directory structure.

For this directory:
1. How should code be organized?
2. What naming conventions?
3. What files should exist at creation?
4. Any boilerplate to include?
```

**Closing Prompt**:
```
Please finalize the repository structure:
1. Complete directory tree
2. All configuration files content
3. README template
4. Setup instructions for new developers
5. Format using repository structure template
```

---

### Pattern 2: CI/CD Pipeline Setup

**When to Use**: Creating continuous integration and deployment pipelines

**Opening Prompt**:
```
I need to set up CI/CD pipelines for [project].

Architecture Context:
[Deployment architecture from Phase 1]

Requirements:
- CI platform: [GitHub Actions / Azure DevOps / GitLab / Jenkins / etc.]
- Environments: [dev, staging, prod]
- Deployment target: [Cloud provider, Kubernetes, etc.]
- Quality gates from constitution: [List key requirements]

Please design CI/CD pipelines including:
1. Build pipeline (compile, lint, test)
2. Quality gates (coverage, security scans)
3. Artifact creation (Docker images, packages)
4. Deployment pipeline (per environment)
5. Rollback procedure
6. Notifications and alerts
```

**Pipeline Deep Dive**:
```
Let's detail the [build/deploy/specific] pipeline.

Please provide:
1. Step-by-step pipeline stages
2. Trigger conditions
3. Environment variables needed
4. Secrets management approach
5. Failure handling
6. Actual pipeline configuration (YAML or equivalent)
```

**Quality Gates Prompt**:
```
From the constitution, these quality standards must be enforced:
[List from constitution]

Please configure quality gates:
1. Which checks run in CI vs. CD
2. What thresholds fail the build
3. What's blocking vs. warning
4. How to handle flaky tests
5. Security scanning configuration
```

**Closing Prompt**:
```
Please finalize the CI/CD configuration:
1. All pipeline definitions (actual YAML/config)
2. Quality gate configurations
3. Environment-specific settings
4. Secrets list (what needs to be configured)
5. Troubleshooting guide for common failures
```

---

### Pattern 3: Development Environment Setup

**When to Use**: Creating consistent development environments

**Opening Prompt**:
```
I need to set up development environments for [project].

Team Setup:
- Team size: [N] developers
- Operating systems: [Mac / Windows / Linux mix]
- IDEs: [VS Code / IntelliJ / etc.]

Tech Stack:
[List from architecture]

Requirements:
- New developer should be productive in: [X hours target]
- Environment parity with production: [High / Medium]
- Local vs. remote development: [Preference]

Please design the development environment:
1. Prerequisites to install
2. Setup script/automation
3. IDE configuration (extensions, settings)
4. Local services (database, cache, etc.)
5. Environment variables
6. Sample data/seeds
7. Verification steps
```

**DevContainer/Docker Compose Prompt**:
```
Let's create containerized development environment.

Please configure:
1. docker-compose.yml for local development
2. DevContainer configuration (for VS Code)
3. Service dependencies (database, cache, message queue)
4. Volume mounts for hot reload
5. Network configuration
6. Health checks
```

**Closing Prompt**:
```
Please finalize development environment setup:
1. Complete setup documentation
2. All configuration files
3. Setup scripts
4. Verification checklist
5. Troubleshooting guide
6. Format using environment config template
```

---

### Pattern 4: Docker Configuration

**When to Use**: Creating containerization for the application

**Opening Prompt**:
```
I need to containerize [project].

Application Architecture:
[Components that need containerization]

Requirements:
- Base images: [Preferences]
- Image size: [Optimized / Standard]
- Multi-stage builds: [Yes / No]
- Security: [Scan requirements from constitution]

Please create Docker configuration:
1. Dockerfile for each component
2. Multi-stage build optimization
3. Security hardening (non-root user, minimal base)
4. Build arguments and environment variables
5. Health checks
6. docker-compose for local development
```

**Optimization Prompt**:
```
Let's optimize the Docker configuration.

Current Dockerfile:
[Paste current]

Please optimize for:
1. Smaller image size
2. Faster builds (layer caching)
3. Security (vulnerabilities, permissions)
4. Production readiness
```

**Closing Prompt**:
```
Please finalize Docker configuration:
1. All Dockerfiles (production-ready)
2. docker-compose.yml files (dev and prod)
3. .dockerignore
4. Build documentation
5. Image tagging strategy
```

---

### Pattern 5: Cloud Infrastructure Setup

**When to Use**: Setting up cloud resources and infrastructure as code

**Opening Prompt**:
```
I need to set up cloud infrastructure for [project].

Cloud Provider: [AWS / Azure / GCP]

Architecture Requirements:
[From Phase 1 architecture - compute, database, networking needs]

Environments:
- Development: [Requirements]
- Staging: [Requirements]
- Production: [Requirements]

Infrastructure as Code:
- Tool preference: [Terraform / Pulumi / CloudFormation / Bicep]
- State management: [Remote state approach]

Please design infrastructure including:
1. Compute resources (containers, VMs, serverless)
2. Database resources
3. Networking (VPC, subnets, security groups)
4. Storage
5. CDN/Load balancing
6. Monitoring resources
7. IAM/Security configuration
```

**IaC Deep Dive**:
```
Let's create the infrastructure code for [specific resource/environment].

Please provide:
1. Resource definitions (Terraform/etc.)
2. Variables and outputs
3. Module structure (if applicable)
4. State configuration
5. Deployment instructions
```

**Closing Prompt**:
```
Please finalize cloud infrastructure setup:
1. All IaC files organized by module/environment
2. Variable definitions
3. Deployment pipeline integration
4. Cost estimation (rough)
5. Security review checklist
6. Disaster recovery considerations
```

---

### Pattern 6: Developer Onboarding Guide

**When to Use**: Creating documentation for new team members

**Opening Prompt**:
```
I need to create a developer onboarding guide for [project].

Target audience:
- Experience level: [Junior / Mid / Senior]
- Expected ramp-up time: [X days/hours]

What they need to know:
1. How to set up development environment
2. How to run the application locally
3. How to run tests
4. How to create a PR
5. Architecture overview
6. Coding standards
7. Who to ask for help

Please create comprehensive onboarding documentation.
```

**Quick Start Focus**:
```
Create a "5-minute quick start" for developers who just want to run the app.

Assume:
- Git is installed
- [Language runtime] is installed
- [Tool X] is installed

Steps should be copy-paste ready.
```

**Closing Prompt**:
```
Please finalize onboarding documentation:
1. README.md quick start section
2. Detailed setup guide
3. Architecture overview for developers
4. Contribution guidelines
5. FAQ / Troubleshooting
6. Key contacts and resources
```

---

## Best Practices for This Mode

### Do's
- ✅ Automate everything possible
- ✅ Make setup reproducible
- ✅ Document all prerequisites
- ✅ Include troubleshooting guides
- ✅ Test setup on clean machine
- ✅ Follow security best practices
- ✅ Keep configuration in version control
- ✅ Use environment variables for secrets

### Don'ts
- ❌ Don't hardcode secrets or credentials
- ❌ Don't assume tools are installed
- ❌ Don't skip quality gates in CI
- ❌ Don't create environment drift between dev/prod
- ❌ Don't forget rollback procedures
- ❌ Don't over-engineer for day 1

---

## Session Outputs

### Primary Artifacts
- **Repository Structure** (`repository-structure.md`):
  - Directory layout
  - Configuration files
  - Templates (PR, issues)
  - Branch strategy

- **CI/CD Configuration**:
  - Pipeline definitions
  - Quality gates
  - Deployment procedures

- **Environment Configuration** (`environment-config.md`):
  - Setup instructions
  - Docker configurations
  - Infrastructure as code

- **Developer Onboarding Guide**:
  - Quick start
  - Detailed setup
  - Troubleshooting

### Actual Files to Create
- Dockerfile(s)
- docker-compose.yml
- CI/CD pipeline files (.github/workflows/, azure-pipelines.yml, etc.)
- terraform/pulumi/cloudformation files
- README.md
- CONTRIBUTING.md
- Setup scripts

---

## Quality Checks Before Ending Session

- [ ] Repository structure documented
- [ ] CI/CD pipelines configured
- [ ] Quality gates match constitution requirements
- [ ] Development environment setup tested
- [ ] Docker configuration complete
- [ ] Onboarding documentation clear
- [ ] New developer can set up in target time
- [ ] All configuration files ready
- [ ] No secrets in code
- [ ] Rollback procedure documented

---

## Transitioning Out of This Mode

**When Infrastructure is Ready**:
- Repository created and accessible
- CI/CD pipelines functional
- Development environment works
- Team can start Sprint 0

**Validation Prompt**:
```
Please create an infrastructure readiness checklist:
1. Repository access verified
2. CI pipeline runs successfully
3. CD pipeline deploys to dev
4. Development environment works on [N] machines
5. Quality gates are enforcing
6. Documentation is accessible
7. Team has been onboarded
```

**Handoff to Development**:
```
Infrastructure setup is complete. Please create Sprint 0 kickoff documentation:
1. Repository URL and access instructions
2. CI/CD status and how to monitor
3. Development environment quick start
4. First tasks developers should do
5. Known issues or workarounds
6. Support contacts for infrastructure issues
```

---

*Created for: Phase 2 - Planning & Setup*
*Works with: DevOps Scaffolder Agent*
*Last Updated: 2025-12-15*
