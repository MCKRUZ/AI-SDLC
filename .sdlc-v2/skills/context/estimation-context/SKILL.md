---
name: estimation-context
description: >
  Cost estimation and resource planning context including hourly rates,
  pod structures (Staff through Managing Director), and estimation models.
  Use when creating estimates, resource plans, or discussing costs.
---
# Estimation Context

## Purpose

Provides reference data for accurate cost estimation and resource planning.

## Pod Structures

See [pod-structures.reference.md](pod-structures.reference.md) for staffing models:

| Level | Role | Typical Allocation |
|-------|------|-------------------|
| Staff | Junior developer | 100% |
| Senior | Senior developer | 100% |
| Manager | Tech lead | 75% |
| Senior Manager | Architect | 50% |
| Managing Director | Engagement lead | 25% |

## Rate Cards

See [rate-cards.reference.md](rate-cards.reference.md) for:
- Hourly rates by level
- Blended rates by pod composition
- Offshore/onshore differentials

## Estimation Models

### ROM (Rough Order of Magnitude)
- **Accuracy**: -25% to +75%
- **When**: Early discovery, before requirements
- **Method**: Analogous estimation from similar projects

### Budgetary
- **Accuracy**: -15% to +25%
- **When**: After requirements, before detailed design
- **Method**: Parametric estimation with adjustments

### Definitive
- **Accuracy**: -5% to +10%
- **When**: After detailed planning
- **Method**: Bottom-up from task estimates

## Key Principles

1. **People Costs Dominate**: 60-70% of total investment
2. **Progressive Refinement**: ROM → Budgetary → Definitive
3. **Risk-Adjusted**: Include contingency for uncertainty
4. **Capacity-Based**: Align with available resources

## When to Load

- Phase 0: Early ROM estimates
- Phase 2: Resource planning
- When discussing budget with stakeholders