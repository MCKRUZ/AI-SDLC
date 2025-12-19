# C4 Model Reference

## Overview

The C4 model provides a hierarchical approach to visualizing software
architecture at different levels of abstraction.

**C4 = Context, Containers, Components, Code**

---

## Level 1: System Context Diagram

### Purpose

Shows how your system fits into the world. Answers: "What is this system
and who uses it?"

### Audience

- Everyone: technical and non-technical stakeholders
- Ideal for: executive presentations, onboarding, scope discussions

### Elements

| Element | Description | Visual |
|---------|-------------|--------|
| Person | A user of the system | Stick figure or labeled box |
| Software System | Your system (the focus) | Large box (highlighted) |
| External System | Systems you integrate with | Box (different color) |
| Relationship | How elements interact | Arrow with label |

### Example

```
┌─────────────┐         ┌─────────────────────────┐
│   Customer  │         │    Email System         │
│   (Person)  │         │  (External System)      │
└──────┬──────┘         └───────────▲─────────────┘
       │                            │
       │ Views orders,              │ Sends order
       │ places orders              │ confirmations
       ▼                            │
┌──────────────────────────────────────────────────┐
│                                                  │
│              E-Commerce System                   │
│                (Your System)                     │
│                                                  │
└──────────────────────────────────────────────────┘
       │                            ▲
       │ Processes payments         │ Retrieves
       ▼                            │ inventory
┌─────────────────┐         ┌───────┴─────────────┐
│  Payment Gateway │         │   Warehouse System  │
│ (External System)│         │  (External System)  │
└─────────────────┘         └─────────────────────┘
```

### Best Practices

- Keep it simple (5-10 elements maximum)
- Focus on high-level interactions
- Use consistent notation
- Label all relationships with verbs
- Highlight your system visually

---

## Level 2: Container Diagram

### Purpose

Shows the major technical building blocks inside your system. Answers:
"What are the main parts and how do they communicate?"

### Audience

- Technical stakeholders
- Ideal for: architecture discussions, technology decisions

### Elements

| Element | Description | Examples |
|---------|-------------|----------|
| Container | A runnable/deployable unit | Web app, API, database, queue |
| Person | Users (from Level 1) | Same as context diagram |
| External System | External systems (from Level 1) | Same as context diagram |

### Container Types

- **Web Application**: Server-side rendered UI (Java, .NET, Node.js)
- **Single Page Application**: Client-side UI (React, Angular, Vue)
- **Mobile App**: iOS, Android application
- **API Application**: REST/GraphQL service
- **Database**: Relational, NoSQL, file storage
- **Message Queue**: Async communication (RabbitMQ, Kafka)
- **Serverless Function**: Lambda, Azure Functions

### Example

```
┌─────────────┐
│   Customer  │
└──────┬──────┘
       │ HTTPS
       ▼
┌──────────────────────────────────────────────────────┐
│                  E-Commerce System                    │
│  ┌─────────────────┐      ┌─────────────────┐        │
│  │   Web App       │      │  Mobile App     │        │
│  │   (React SPA)   │      │  (React Native) │        │
│  └────────┬────────┘      └────────┬────────┘        │
│           │ HTTPS/JSON             │ HTTPS/JSON      │
│           ▼                        ▼                 │
│  ┌─────────────────────────────────────────┐         │
│  │            API Gateway                   │         │
│  │            (Kong)                        │         │
│  └─────────────────┬───────────────────────┘         │
│                    │                                  │
│      ┌─────────────┼─────────────┐                   │
│      ▼             ▼             ▼                   │
│  ┌───────┐    ┌────────┐    ┌─────────┐              │
│  │ Order │    │ Product│    │ User    │              │
│  │Service│    │Service │    │ Service │              │
│  │(Node) │    │(.NET)  │    │ (Node)  │              │
│  └───┬───┘    └───┬────┘    └────┬────┘              │
│      │            │              │                   │
│      ▼            ▼              ▼                   │
│  ┌───────┐    ┌────────┐    ┌─────────┐              │
│  │Orders │    │Products│    │ Users   │              │
│  │  DB   │    │   DB   │    │   DB    │              │
│  │(Postgres)  │(Postgres)   │(Postgres)│             │
│  └───────┘    └────────┘    └─────────┘              │
└──────────────────────────────────────────────────────┘
```

### Best Practices

- Show technology choices in parentheses
- Include communication protocols on arrows
- Keep to 10-15 containers maximum
- Group related containers visually
- Show data stores explicitly

---

## Level 3: Component Diagram

### Purpose

Shows the internal structure of a single container. Answers: "What are
the major structural building blocks inside this container?"

### Audience

- Development team
- Ideal for: detailed design, code organization discussions

### When to Create

- For complex containers only
- When onboarding developers
- When making significant design decisions

### Elements

| Element | Description | Examples |
|---------|-------------|----------|
| Component | A logical grouping of code | Controller, Service, Repository |
| Container | The container being decomposed | From Level 2 |
| External | Other containers/systems it talks to | Databases, other services |

### Example (Order Service)

```
┌────────────────────────────────────────────────────────────┐
│                     Order Service                           │
│  ┌────────────────┐    ┌────────────────┐                  │
│  │ Order          │    │ Payment        │                  │
│  │ Controller     │───▶│ Controller     │                  │
│  └───────┬────────┘    └───────┬────────┘                  │
│          │                     │                           │
│          ▼                     ▼                           │
│  ┌────────────────┐    ┌────────────────┐                  │
│  │ Order          │    │ Payment        │                  │
│  │ Service        │───▶│ Service        │                  │
│  └───────┬────────┘    └───────┬────────┘                  │
│          │                     │                           │
│          ▼                     │                           │
│  ┌────────────────┐            │                           │
│  │ Order          │            │                           │
│  │ Repository     │            │                           │
│  └───────┬────────┘            │                           │
└──────────┼─────────────────────┼───────────────────────────┘
           │                     │
           ▼                     ▼
    ┌─────────────┐      ┌──────────────────┐
    │  Orders DB  │      │ Payment Gateway  │
    └─────────────┘      └──────────────────┘
```

### Best Practices

- Only create for complex containers
- Show key components (not every class)
- Include external dependencies
- Use consistent naming patterns

---

## Level 4: Code Diagram

### Purpose

Shows the actual code structure (classes, interfaces). Usually generated
from code, not manually created.

### When to Use

- Auto-generated from IDE
- For very complex algorithms
- Rarely created manually

### Recommendation

Skip Level 4 in most cases. Use IDE tools or code documentation instead.

---

## Diagram Guidelines

### Notation

```
┌─────────────────────────┐
│ [Element Type]          │
│ Name                    │
│ [Technology]            │
│                         │
│ Description of purpose  │
└─────────────────────────┘
```

### Color Coding (Suggested)

| Color | Usage |
|-------|-------|
| Blue | Your system's elements |
| Gray | External systems |
| Green | Databases/storage |
| Orange | Message queues |

### Relationship Labels

Always label arrows with:
- **Verb**: "reads from", "writes to", "sends to"
- **Protocol**: [HTTPS], [gRPC], [AMQP]
- **Format**: JSON, XML, Binary

---

## Creating C4 Diagrams

### Tools

- **Structurizr**: Purpose-built for C4
- **PlantUML**: With C4 extension
- **Mermaid**: With C4 support
- **Draw.io**: Manual with shapes
- **Lucidchart**: With C4 template

### PlantUML Example

```plantuml
@startuml
!include C4_Container.puml

Person(customer, "Customer", "A user of our system")
System_Boundary(c1, "E-Commerce System") {
    Container(web_app, "Web App", "React", "Provides UI")
    Container(api, "API", "Node.js", "Handles requests")
    ContainerDb(db, "Database", "PostgreSQL", "Stores data")
}
System_Ext(email, "Email System", "Sends emails")

Rel(customer, web_app, "Uses", "HTTPS")
Rel(web_app, api, "Calls", "HTTPS/JSON")
Rel(api, db, "Reads/Writes", "SQL")
Rel(api, email, "Sends via", "SMTP")
@enduml
```

---

## Quick Reference

### Which Level When?

| Audience | Level |
|----------|-------|
| Executives, stakeholders | Level 1 (Context) |
| Architects, tech leads | Level 2 (Container) |
| Development team | Level 3 (Component) |
| Code review | Level 4 (Code) - rarely |

### Checklist

- [ ] Level 1 context diagram created
- [ ] All external systems identified
- [ ] Level 2 container diagram created
- [ ] Technology choices documented
- [ ] Communication protocols labeled
- [ ] Level 3 created for complex containers
- [ ] Diagrams reviewed with team
