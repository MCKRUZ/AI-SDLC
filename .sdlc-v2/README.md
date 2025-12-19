# AI-SDLC v2 - Skills-Based Architecture

This is the v2 implementation of the AI-SDLC methodology using
Anthropic's Agent Skills format.

## Structure

skills/
├── phase0/ # Discovery & Feasibility
├── phase1/ # Specification & Design
├── phase2/ # Planning & Setup
├── phase3/ # Implementation
└── context/ # Cross-phase context

## Naming Conventions

| Type      | Suffix          | Example                             |
| --------- | --------------- | ----------------------------------- |
| Activity  | `-activity`     | `stakeholder-discovery-activity/`   |
| Context   | `-context`      | `organization-context/`             |
| Template  | `.template.md`  | `interview-transcript.template.md`  |
| Reference | `.reference.md` | `interview-techniques.reference.md` |

## Usage

Each phase contains self-contained activity skills. Load a phase skill
to see available activities, then load specific activities as needed.

### Example Flow

1. Load `phase0/SKILL.md` to see Phase 0 activities
2. Load `phase0/stakeholder-discovery-activity/SKILL.md` for interviews
3. Use templates from `templates/` folder within the activity
