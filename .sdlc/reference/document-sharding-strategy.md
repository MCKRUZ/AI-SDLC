# Document Sharding Strategy

**Version**: 1.0  
**Last Updated**: 2025-12-13  
**Purpose**: Strategy for breaking large artifacts into focused, context-efficient chunks  
**Location**: `.sdlc/reference/document-sharding-strategy.md`

---

## Overview

Large SDLC artifacts (PRDs, Architecture docs, Specifications) often exceed practical context window limits for AI agents. **Document Sharding** breaks these into focused chunks that can be loaded on-demand, reducing token usage by up to 90% while maintaining coherence.

### The Problem

```
Full Architecture Document: ~15,000 tokens
Full PRD: ~8,000 tokens
Full Spec: ~12,000 tokens
Total for one session: ~35,000 tokens (just artifacts!)

+ Agent instructions: ~3,000 tokens
+ Conversation: ~5,000 tokens
= 43,000+ tokens before you've done any work
```

### The Solution

```
Sharded Architecture (relevant section only): ~1,500 tokens
Sharded PRD (relevant feature): ~800 tokens  
Sharded Spec (relevant stories): ~1,200 tokens
Total: ~3,500 tokens (90% reduction)

+ Agent instructions: ~3,000 tokens
+ Conversation: ~5,000 tokens
= 11,500 tokens - plenty of room for work
```

---

## Sharding Principles

### 1. Shard by Consumer, Not by Source

Don't shard based on how the document was written. Shard based on who needs what.

```
❌ Wrong: Shard architecture.md into "Section 1", "Section 2", "Section 3"

✅ Right: Shard architecture.md by:
   - Component/Service (for stories touching that component)
   - Integration (for stories involving that integration)
   - Data Domain (for stories using that data)
```

### 2. Shards are Self-Contained

Each shard should make sense on its own without requiring other shards.

```
❌ Wrong: "See section 3.2 for details" (reference to content not in shard)

✅ Right: Include all necessary context within the shard, even if slightly duplicated
```

### 3. Shards Include Source Metadata

Every shard must link back to its source for traceability.

```markdown
---
Source: phase1/artifacts/architecture.md
Sections: 3.2 Authentication Service, 5.1 User Data Model
Sharded: 2025-12-13
Shard ID: arch-auth-001
---
```

### 4. Shards are Versioned with Source

When the source document changes, affected shards must be regenerated.

```markdown
Source Version: 2.3 (last modified: 2025-12-10)
Shard Valid For: Source versions 2.x
Regenerate If: Source version 3.x or major changes to included sections
```

---

## Sharding Strategies by Document Type

### PRD Sharding

**Master Document**: `phase1/artifacts/prd.md`  
**Shard Directory**: `phase1/shards/prd/`

#### Shard Structure

```
phase1/shards/prd/
├── _index.md                    # Shard index with quick reference
├── vision-and-goals.shard.md   # Vision, goals, success metrics
├── epic-[name].shard.md        # One shard per epic
├── personas.shard.md           # User personas
├── constraints.shard.md        # Business/technical constraints
└── mvp-definition.shard.md     # MVP scope definition
```

#### PRD Shard Template

```markdown
# PRD Shard: [Epic/Feature Name]

---
**Source**: phase1/artifacts/prd.md
**Sections**: [List of sections included]
**Sharded**: [Date]
**Source Version**: [Version]
---

## Context (from PRD)

### Product Vision (Summary)
[2-3 sentence summary of overall vision - always include for context]

### This Epic/Feature

#### Description
[Full description from PRD]

#### User Value
[Why users need this]

#### Business Value  
[Why business needs this]

### User Personas (Relevant)
[Only personas that interact with this feature]

### Success Metrics (Relevant)
[Only metrics that apply to this feature]

### Constraints (Relevant)
[Only constraints that affect this feature]

### Dependencies
[Dependencies on other features/systems]

---
**Cross-References**:
- Related Epic Shards: [list]
- Architecture Shard: [link]
- Spec Shard: [link]
```

---

### Architecture Sharding

**Master Document**: `phase1/artifacts/architecture.md`  
**Shard Directory**: `phase1/shards/architecture/`

#### Shard Structure

```
phase1/shards/architecture/
├── _index.md                        # Component/service index
├── system-overview.shard.md        # C4 Context + Container (always load)
├── component-[name].shard.md       # One shard per component/service
├── integration-[name].shard.md     # One shard per external integration
├── data-domain-[name].shard.md     # One shard per data domain
└── cross-cutting-[name].shard.md   # Security, logging, monitoring, etc.
```

#### Component Shard Template

```markdown
# Architecture Shard: [Component/Service Name]

---
**Source**: phase1/artifacts/architecture.md
**Sections**: [Sections included]
**Sharded**: [Date]
**Source Version**: [Version]
**Related Components**: [List of related components]
---

## System Context (Always Included)

### Where This Component Fits
[1-2 paragraphs from C4 Context showing this component's role]

```
[Simple diagram showing this component in context]
Component A ──► [THIS COMPONENT] ──► Component B
                     │
                     ▼
               External System
```

## Component Details

### Purpose
[What this component does]

### Responsibilities
- [Responsibility 1]
- [Responsibility 2]
- [Responsibility 3]

### Technology Stack
- Language: [X]
- Framework: [Y]
- Key Libraries: [Z]

### Interfaces

#### Inbound
| Interface | Type | Description |
|-----------|------|-------------|
| [API/Event/etc] | [REST/gRPC/Queue] | [What it does] |

#### Outbound
| Interface | Target | Type | Description |
|-----------|--------|------|-------------|
| [Name] | [Target] | [Type] | [What it does] |

## Data Model (Relevant Entities)

```
[Entity 1]
├── field1: type
├── field2: type
└── → [Entity 2] (relationship)
```

## Key Patterns Used

### [Pattern Name]
[How this pattern is applied in this component]

## Configuration

| Setting | Purpose | Default |
|---------|---------|---------|
| [Setting] | [Why needed] | [Value] |

## Deployment

[How this component is deployed - container, serverless, etc.]

---
**Cross-References**:
- Integration Shards: [list relevant integrations]
- Data Domain Shards: [list relevant data domains]
- ADRs: [list relevant ADRs]
```

#### Integration Shard Template

```markdown
# Architecture Shard: [Integration Name] Integration

---
**Source**: phase1/artifacts/architecture.md
**Sections**: [Sections included]
**Sharded**: [Date]
**Source Version**: [Version]
---

## Integration Overview

### External System
- **Name**: [External system name]
- **Type**: [Third-party SaaS / Internal System / Partner API]
- **Owner**: [Who owns the external system]

### Integration Purpose
[Why we integrate with this system]

### Integration Pattern
[Sync/Async, Request-Response/Event-Driven, etc.]

## Technical Details

### Connection
- **Protocol**: [REST/gRPC/SOAP/Queue/etc.]
- **Authentication**: [OAuth/API Key/mTLS/etc.]
- **Base URL**: [URL pattern]

### API Contract

#### We Call Them
```yaml
endpoint: [METHOD] [/path]
purpose: [What we use this for]
request:
  headers:
    Authorization: Bearer {token}
  body:
    field: type
response:
  200:
    field: type
  error_codes:
    - 400: [When]
    - 401: [When]
```

#### They Call Us (Webhooks/Callbacks)
```yaml
endpoint: [METHOD] [/our-path]
purpose: [What they notify us about]
payload:
  field: type
```

### Error Handling
- **Retry Strategy**: [X retries with Y backoff]
- **Circuit Breaker**: [Threshold and behavior]
- **Fallback**: [What happens when integration fails]

### Rate Limits
- **Their Limits**: [X requests per Y time]
- **Our Throttling**: [How we stay under limits]

## Data Flow

```
Our System                    External System
    │                              │
    │──── Request ────────────────►│
    │                              │
    │◄─── Response ───────────────│
    │                              │
```

## Components Using This Integration
- [Component A] - [How it uses the integration]
- [Component B] - [How it uses the integration]

---
**Cross-References**:
- Component Shards: [list]
- Data Domain Shards: [list]
```

---

### Specification Sharding

**Master Document**: `phase1/artifacts/spec.md`  
**Shard Directory**: `phase1/shards/spec/`

#### Shard Structure

```
phase1/shards/spec/
├── _index.md                    # Story index by epic/feature
├── epic-[name]/                 # Directory per epic
│   ├── epic-overview.shard.md  # Epic summary
│   ├── story-[id].shard.md     # Individual story shards
│   └── acceptance-matrix.md    # All acceptance criteria for epic
└── nfr/                         # Non-functional requirements
    ├── performance.shard.md
    ├── security.shard.md
    └── accessibility.shard.md
```

#### Story Shard Template

```markdown
# Spec Shard: [Story ID] - [Story Title]

---
**Source**: phase1/artifacts/spec.md
**Section**: Epic: [Name], Story: [ID]
**Sharded**: [Date]
**Source Version**: [Version]
---

## User Story

**As a** [persona],  
**I want** [goal],  
**So that** [benefit].

## Acceptance Criteria

```gherkin
Feature: [Feature name]

  Scenario: [Happy path]
    Given [context]
    When [action]
    Then [outcome]

  Scenario: [Alternative path]
    Given [context]
    When [action]
    Then [outcome]

  Scenario: [Error case]
    Given [context]
    When [action]
    Then [error handling]
```

## Business Rules
- [Rule 1]
- [Rule 2]

## UI/UX Notes
[Any UI requirements or mockup references]

## Technical Notes
[Any technical requirements or constraints]

## Dependencies
- [Story X] - [Why]

---
**Cross-References**:
- PRD Shard: [epic shard link]
- Architecture Shard: [relevant component]
```

---

## Shard Index Files

Every shard directory needs an `_index.md` for navigation:

```markdown
# [Document Type] Shard Index

**Source Document**: [path to master]
**Last Sharded**: [date]
**Source Version**: [version]

## Quick Reference

| Shard | Content | Size | Use When |
|-------|---------|------|----------|
| [shard-name] | [summary] | [~X tokens] | [when to load] |

## Shard Map

### By Component
- Component A → [shard link]
- Component B → [shard link]

### By Epic/Feature
- Epic 1 → [shard link]
- Epic 2 → [shard link]

### By Data Domain
- Users → [shard link]
- Orders → [shard link]

## Loading Guide

### For Story Implementation
Load:
1. `system-overview.shard.md` (always)
2. `component-[affected].shard.md`
3. `story-[id].shard.md`

### For Integration Work
Load:
1. `system-overview.shard.md` (always)
2. `integration-[name].shard.md`
3. `component-[calling].shard.md`

### For Data Model Work
Load:
1. `data-domain-[name].shard.md`
2. `component-[using].shard.md`
```

---

## Sharding Workflow

### When to Shard

```
┌─────────────────────────────────────────────────────────────────┐
│                    SHARDING DECISION TREE                        │
└─────────────────────────────────────────────────────────────────┘

Is the document > 3,000 tokens?
         │
    ┌────┴────┐
    No        Yes
    │          │
    ▼          ▼
Keep as-is   Will multiple agents/stories need different parts?
                   │
              ┌────┴────┐
              No        Yes
              │          │
              ▼          ▼
         Keep as-is   SHARD IT
         (load in 
          full when 
          needed)
```

### How to Shard

```markdown
## Sharding Process

### Step 1: Analyze Document Structure
- Identify logical sections
- Map sections to consumers (which agent/story needs what)
- Identify shared context (always include)

### Step 2: Define Shard Boundaries
- Each shard = one logical unit of work
- Minimize cross-references between shards
- Include context summary in each shard

### Step 3: Create Shard Index
- List all shards with summaries
- Provide loading guidance
- Map shards to use cases

### Step 4: Extract Shards
- Copy relevant sections
- Add source metadata header
- Add cross-references
- Verify shard is self-contained

### Step 5: Validate Shards
- Each shard makes sense alone
- Source links work
- Token counts are reasonable (<2,000 per shard ideal)
```

---

## Token Budget Guidelines

### Target Sizes

| Shard Type | Target Tokens | Maximum Tokens |
|------------|---------------|----------------|
| System Overview | 500-800 | 1,200 |
| Component Shard | 800-1,500 | 2,500 |
| Integration Shard | 600-1,000 | 1,500 |
| Epic Shard | 500-1,000 | 1,500 |
| Story Shard | 300-600 | 1,000 |
| Data Domain Shard | 400-800 | 1,200 |

### Loading Combinations

| Activity | Typical Shards | Total Tokens |
|----------|----------------|--------------|
| Story Implementation | Overview + Component + Story | 1,500-3,000 |
| Integration Work | Overview + Integration + 2 Components | 2,000-4,000 |
| Architecture Review | Overview + 3-4 Components | 2,500-5,000 |
| Full Epic Planning | Epic + All Epic Stories | 2,000-4,000 |

---

## Maintaining Shards

### When to Regenerate

```yaml
regeneration_triggers:
  immediate:
    - Source document major version change
    - Section significantly rewritten
    - New component/integration added
    
  deferred:
    - Minor typo fixes in source
    - Formatting changes
    - Comment additions
    
  automatic_check:
    - Before each sprint (validate all shards current)
    - After architecture review sessions
```

### Shard Version Tracking

```markdown
## Shard Header Version Tracking

---
**Source**: phase1/artifacts/architecture.md
**Source Version**: 2.3
**Source Hash**: abc123... (first 8 chars of file hash)
**Sharded**: 2025-12-13
**Shard Version**: 1.0
**Last Validated**: 2025-12-13
---

## Validation Check

Compare source hash to current file:
- If match: Shard is current
- If different: Review source changes, regenerate if needed
```

---

## Automation Support

### Sharding Script (Concept)

```bash
#!/bin/bash
# shard-document.sh

# Usage: ./shard-document.sh <source-file> <shard-config>

# Read shard configuration
# Extract sections based on config
# Generate shard files with headers
# Update shard index
# Report token counts
```

### Orchestrator Integration

```json
{
  "sharding": {
    "enabled": true,
    "autoShard": {
      "threshold": 3000,
      "strategy": "by-component"
    },
    "shardDirectory": "phase1/shards/",
    "indexFile": "_index.md",
    "validation": {
      "onLoad": true,
      "warnIfStale": true,
      "maxAge": "7d"
    }
  }
}
```

---

## Anti-Patterns

### ❌ Don't: Shard by Page/Section Number

```markdown
# Wrong: architecture-section-1.shard.md
Contains: Introduction, Table of Contents, Overview...
Problem: Useless mix of content
```

### ❌ Don't: Create Cross-Dependent Shards

```markdown
# Wrong: Shard A says "See Shard B for data model"
Problem: Must load both, defeats purpose
```

### ❌ Don't: Over-Shard

```markdown
# Wrong: 50 tiny shards of 100 tokens each
Problem: Index overhead, cognitive load, lost coherence
```

### ❌ Don't: Forget Context

```markdown
# Wrong: Component shard with no system context
Problem: Reader doesn't know where component fits
```

### ✅ Do: Shard by Consumer Need

```markdown
# Right: authentication-service.shard.md
Contains: Everything needed to work on auth service
Self-contained: Yes
```

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | 2025-12-13 | Initial version |
