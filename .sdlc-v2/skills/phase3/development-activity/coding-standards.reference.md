# Coding Standards Reference

## Overview

Consistent coding standards improve readability, maintainability, and
collaboration. These guidelines should be enforced through tooling.

---

## General Principles

### Clean Code

| Principle | Meaning |
|-----------|---------|
| DRY | Don't Repeat Yourself |
| KISS | Keep It Simple, Stupid |
| YAGNI | You Aren't Gonna Need It |
| SRP | Single Responsibility Principle |

### Code Quality Priorities

1. **Correctness** - Does it work?
2. **Clarity** - Can others understand it?
3. **Simplicity** - Is it as simple as possible?
4. **Performance** - Is it fast enough?

---

## Naming Conventions

### General Rules

- Be descriptive over short
- Use domain terminology
- Avoid abbreviations (except common ones)
- Be consistent

### Naming Patterns

| Type | Convention | Example |
|------|------------|---------|
| Classes | PascalCase | `UserService` |
| Methods | camelCase | `getUserById()` |
| Variables | camelCase | `userName` |
| Constants | UPPER_SNAKE | `MAX_RETRY_COUNT` |
| Files | kebab-case | `user-service.ts` |
| Booleans | is/has/can prefix | `isActive`, `hasPermission` |

### What to Avoid

```javascript
// Bad
const d = new Date();  // What is d?
const temp = getData(); // Temp what?
const flag = true;      // What flag?

// Good
const currentDate = new Date();
const userProfile = getData();
const isEmailVerified = true;
```

---

## Code Organization

### File Structure

```
src/
├── components/     # UI components
├── services/       # Business logic
├── models/         # Data models
├── utils/          # Helper functions
├── hooks/          # Custom hooks
├── types/          # Type definitions
└── constants/      # App constants
```

### Function Length

- **Ideal**: 10-20 lines
- **Maximum**: 50 lines
- **If longer**: Extract helper functions

### File Length

- **Ideal**: 100-200 lines
- **Maximum**: 400 lines
- **If longer**: Split into multiple files

---

## Comments and Documentation

### When to Comment

| Do Comment | Don't Comment |
|------------|---------------|
| Why (reasoning) | What (obvious code) |
| Complex algorithms | Simple operations |
| Business rules | Self-explanatory names |
| Workarounds | Every line |

### Documentation

```javascript
/**
 * Calculates the total price including tax and discounts.
 * 
 * @param items - Array of cart items
 * @param taxRate - Tax rate as decimal (e.g., 0.08 for 8%)
 * @returns Total price in cents
 * @throws {InvalidItemError} If any item has invalid price
 */
function calculateTotal(items: CartItem[], taxRate: number): number {
  // Implementation
}
```

---

## Error Handling

### Principles

1. Fail fast
2. Be specific with error types
3. Log errors with context
4. Handle errors at appropriate level

### Pattern

```javascript
// Good
try {
  const user = await userService.getById(id);
  if (!user) {
    throw new NotFoundError(`User ${id} not found`);
  }
  return user;
} catch (error) {
  logger.error('Failed to get user', { id, error });
  throw error; // Re-throw or handle appropriately
}
```

---

## Testing Standards

### Test Naming

```javascript
// Pattern: should_expectedBehavior_when_condition
test('should return null when user not found', () => {});
test('should throw error when email invalid', () => {});
```

### Test Structure (AAA)

```javascript
test('should calculate total correctly', () => {
  // Arrange
  const items = [{ price: 100 }, { price: 200 }];
  
  // Act
  const total = calculateTotal(items);
  
  // Assert
  expect(total).toBe(300);
});
```

### Coverage Targets

| Type | Target |
|------|--------|
| Line coverage | ≥ 80% |
| Branch coverage | ≥ 75% |
| Function coverage | ≥ 90% |

---

## Git Commit Standards

### Commit Message Format

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Types

| Type | Use For |
|------|---------|
| feat | New feature |
| fix | Bug fix |
| docs | Documentation |
| style | Formatting |
| refactor | Code restructuring |
| test | Adding tests |
| chore | Maintenance |

### Examples

```
feat(auth): add password reset functionality

Implements password reset flow with email verification.
Includes rate limiting to prevent abuse.

Closes #123
```

---

## Tool Configuration

### Linting

- ESLint/TSLint for JavaScript/TypeScript
- Run on save and in CI
- No warnings in production code

### Formatting

- Prettier for consistent formatting
- Configure in `.prettierrc`
- Format on save

### Pre-commit Hooks

```json
// package.json
{
  "husky": {
    "hooks": {
      "pre-commit": "lint-staged"
    }
  },
  "lint-staged": {
    "*.ts": ["eslint --fix", "prettier --write"]
  }
}
```

---

## Quick Reference

**Before committing**:
- [ ] Code compiles without errors
- [ ] All tests pass
- [ ] No linting warnings
- [ ] Meaningful commit message
- [ ] Self-reviewed changes
