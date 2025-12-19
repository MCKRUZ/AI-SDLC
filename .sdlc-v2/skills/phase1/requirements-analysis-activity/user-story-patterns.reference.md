# User Story Patterns Reference

## Story Format

### Standard Format

```
As a [user type]
I want to [action/capability]
So that [benefit/value]
```

### Extended Format (with context)

```
As a [user type]
In the context of [situation/workflow]
I want to [action/capability]
So that [benefit/value]
```

---

## Acceptance Criteria Patterns

### Given-When-Then (Gherkin)

Best for behavior-driven scenarios:

```gherkin
Given [precondition/context]
When [action is performed]
Then [expected outcome]
And [additional outcome]
```

**Example:**
```gherkin
Given I am logged in as a premium user
And I have items in my cart
When I proceed to checkout
Then I see the premium discount applied
And the total reflects the 15% reduction
```

### Checklist Format

Best for simple validation:

```markdown
Acceptance Criteria:
- [ ] User can enter email address
- [ ] Email format is validated
- [ ] Error message shown for invalid format
- [ ] Success confirmation displayed
```

### Rule-Based Format

Best for business logic:

```markdown
Rules:
- Discount applies only to orders over $100
- Maximum discount is 25%
- Discount codes expire after 30 days
- Only one discount code per order
```

---

## Story Splitting Patterns

### Split by User Type

**Before (too large):**
```
As a user, I want to manage my account settings
```

**After (split):**
```
As a regular user, I want to update my email address
As an admin user, I want to manage user permissions
As a premium user, I want to configure billing preferences
```

### Split by Operation (CRUD)

**Before:**
```
As a manager, I want to manage employee records
```

**After:**
```
As a manager, I want to create new employee records
As a manager, I want to view employee details
As a manager, I want to update employee information
As a manager, I want to deactivate employee records
```

### Split by Workflow Step

**Before:**
```
As a customer, I want to complete my purchase
```

**After:**
```
As a customer, I want to add items to my cart
As a customer, I want to enter shipping information
As a customer, I want to select payment method
As a customer, I want to review and confirm my order
```

### Split by Business Rule

**Before:**
```
As a seller, I want to set product pricing
```

**After:**
```
As a seller, I want to set base product price
As a seller, I want to configure bulk discounts
As a seller, I want to set promotional pricing with date ranges
As a seller, I want to set member-only pricing
```

### Split by Data Variation

**Before:**
```
As a user, I want to upload documents
```

**After:**
```
As a user, I want to upload PDF documents
As a user, I want to upload image files
As a user, I want to upload spreadsheets
```

### Split by Interface

**Before:**
```
As a user, I want to access my dashboard
```

**After:**
```
As a mobile user, I want to view my dashboard summary
As a desktop user, I want to see detailed dashboard analytics
As an API consumer, I want to retrieve dashboard data
```

### Split by Happy Path / Edge Cases

**Before:**
```
As a user, I want to reset my password
```

**After:**
```
As a user, I want to reset my password via email link
As a user, I want to see an error if reset link is expired
As a user, I want to request a new reset link if needed
```

---

## Story Types

### Feature Stories

Standard user-facing functionality:
```
As a shopper
I want to save items to a wishlist
So that I can purchase them later
```

### Enabler Stories

Technical foundation that enables features:
```
As a development team
We need to set up the authentication service
So that we can implement user login features
```

### Spike Stories

Research/learning with time-boxed exploration:
```
As a development team
We need to investigate payment gateway options
So that we can choose the best integration approach

Time-box: 2 days
Output: Recommendation document with pros/cons
```

### Bug Fix Stories

Correcting existing behavior:
```
As a user
I expect the cart total to update when I change quantity
But currently it only updates on page refresh

Fix: Real-time cart total calculation
```

### Technical Debt Stories

Improving code quality:
```
As a development team
We need to refactor the order processing module
So that we can reduce bug frequency and improve maintainability

Acceptance Criteria:
- Code coverage increased to 80%
- Cyclomatic complexity reduced below 10
- All TODO comments addressed
```

---

## Anti-Patterns to Avoid

### The Epic Disguised as Story

❌ **Bad:**
```
As a user, I want to manage my entire profile
```

✅ **Good:** Split into multiple stories

### The Technical Task

❌ **Bad:**
```
As a developer, I want to refactor the database layer
```

✅ **Good:**
```
As a user, I want faster page loads
So that I don't abandon the site

Technical approach: Optimize database queries
```

### The Vague Story

❌ **Bad:**
```
As a user, I want a better experience
```

✅ **Good:**
```
As a user, I want form fields to show validation errors inline
So that I can correct mistakes without scrolling
```

### The Solution-Specific Story

❌ **Bad:**
```
As a user, I want a React modal with Redux state management
```

✅ **Good:**
```
As a user, I want to confirm my action before deleting items
So that I don't accidentally lose data
```

### Missing "So That"

❌ **Bad:**
```
As a user, I want to filter by date
```

✅ **Good:**
```
As a user, I want to filter reports by date range
So that I can analyze trends for specific periods
```

---

## Story Mapping Template

```
                    User Journey / Workflow
    ┌──────────────────────────────────────────────────────┐
    │  Browse  →  Search  →  Compare  →  Purchase  →  Track │
    └──────────────────────────────────────────────────────┘
         │          │          │           │           │
         ▼          ▼          ▼           ▼           ▼
    ┌────────┐ ┌────────┐ ┌────────┐ ┌──────────┐ ┌────────┐
MVP │ View   │ │ Basic  │ │ Side   │ │ Cart     │ │ Order  │
    │ catalog│ │ search │ │ by side│ │ checkout │ │ status │
    └────────┘ └────────┘ └────────┘ └──────────┘ └────────┘
         │          │          │           │           │
         ▼          ▼          ▼           ▼           ▼
    ┌────────┐ ┌────────┐ ┌────────┐ ┌──────────┐ ┌────────┐
v2  │ Filter │ │ Adv    │ │ Save   │ │ Saved    │ │ Track  │
    │ catalog│ │ search │ │ compare│ │ payment  │ │ shipment│
    └────────┘ └────────┘ └────────┘ └──────────┘ └────────┘
```

---

## Quick Reference

### Story Checklist

Before adding to backlog:

- [ ] Written from user perspective
- [ ] Includes clear benefit ("so that")
- [ ] Has testable acceptance criteria
- [ ] Small enough for single sprint
- [ ] Independent or dependencies documented
- [ ] INVEST score ≥ 9

### Acceptance Criteria Checklist

- [ ] Specific and measurable
- [ ] Covers happy path
- [ ] Addresses key edge cases
- [ ] Includes error scenarios
- [ ] Defines boundary conditions
- [ ] Can be demonstrated in review
