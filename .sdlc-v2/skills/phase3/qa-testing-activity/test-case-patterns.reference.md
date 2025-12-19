# Test Case Patterns Reference

## Overview

Effective test cases systematically verify functionality while being
maintainable and efficient to execute.

---

## Test Case Categories

### Happy Path

Test the normal, expected flow.

```
Given a valid user with items in cart
When they click checkout and enter valid payment
Then order is placed and confirmation shown
```

### Edge Cases

Test boundary conditions and limits.

| Type | Examples |
|------|----------|
| Empty | Empty list, blank input, zero quantity |
| Maximum | Max length, max items, upper limit |
| Minimum | Single character, one item, lower limit |
| Boundary | Just under/over limits |

### Error Cases

Test how system handles failures.

| Scenario | Test |
|----------|------|
| Invalid input | Wrong format, missing required fields |
| Unauthorized | Access without permission |
| Not found | Resource doesn't exist |
| Server error | Simulated backend failure |

### Security Cases

Test for vulnerabilities.

| Test Type | What to Try |
|-----------|-------------|
| Injection | SQL injection, XSS payloads |
| Auth bypass | Direct URL access, token manipulation |
| Authorization | Access other users' data |

---

## Test Case Structure

### Given-When-Then Format

```gherkin
Feature: Shopping Cart

Scenario: Add item to cart
  Given I am logged in as a customer
  And my cart is empty
  When I click "Add to Cart" on product "Widget"
  Then my cart should contain 1 item
  And the cart total should be $19.99
```

### Arrange-Act-Assert Pattern

```javascript
test('adds item to cart', () => {
  // Arrange
  const cart = new Cart();
  const product = { id: 1, price: 19.99 };
  
  // Act
  cart.addItem(product);
  
  // Assert
  expect(cart.items).toHaveLength(1);
  expect(cart.total).toBe(19.99);
});
```

---

## Coverage Patterns

### Equivalence Partitioning

Divide inputs into groups that should behave the same.

| Input | Partition | Test Value |
|-------|-----------|------------|
| Age | Invalid (< 0) | -1 |
| Age | Child (0-12) | 5 |
| Age | Teen (13-19) | 15 |
| Age | Adult (20-64) | 30 |
| Age | Senior (65+) | 70 |

### Boundary Value Analysis

Test at the edges of each partition.

| Boundary | Test Values |
|----------|-------------|
| 0 | -1, 0, 1 |
| 12/13 | 12, 13 |
| 19/20 | 19, 20 |
| 64/65 | 64, 65 |

### Decision Table

| Condition | Case 1 | Case 2 | Case 3 | Case 4 |
|-----------|--------|--------|--------|--------|
| Logged in | Y | Y | N | N |
| Has items | Y | N | Y | N |
| **Result** | Checkout | Empty cart msg | Login prompt | Login prompt |

---

## Common Test Scenarios

### CRUD Operations

| Operation | Happy Path | Edge Cases |
|-----------|------------|------------|
| Create | Valid data | Missing fields, duplicates |
| Read | Existing item | Not found, no permission |
| Update | Valid changes | Concurrent edit, invalid data |
| Delete | Existing item | Not found, has dependencies |

### Authentication

| Scenario | Test |
|----------|------|
| Login success | Valid credentials |
| Login failure | Wrong password, unknown user |
| Session | Timeout, refresh, logout |
| Password reset | Valid flow, expired token |

### Forms

| Test | Description |
|------|-------------|
| Required fields | Submit with missing required |
| Field validation | Invalid formats (email, phone) |
| Character limits | At max, over max |
| Special characters | Quotes, slashes, unicode |

---

## Test Data Management

### Approaches

| Approach | Pros | Cons |
|----------|------|------|
| Fixtures | Consistent, version controlled | Can become stale |
| Factories | Flexible, generates variations | More code to maintain |
| Seeded DB | Realistic | Slower, dependencies |
| Mocks | Fast, isolated | May miss real issues |

### Test Data Guidelines

1. Use realistic but not real data
2. Make data self-describing (test_user@example.com)
3. Reset state between tests
4. Don't depend on test execution order

---

## Test Organization

### Naming Convention

```
should_expectedBehavior_when_condition

// Examples
should_returnError_when_emailInvalid
should_createUser_when_allFieldsValid
should_sendNotification_when_orderPlaced
```

### Grouping

```javascript
describe('UserService', () => {
  describe('create', () => {
    test('should create user when valid data', () => {});
    test('should throw when email exists', () => {});
  });
  
  describe('delete', () => {
    test('should delete user when exists', () => {});
    test('should throw when not found', () => {});
  });
});
```

---

## Quick Reference

**For each feature, test**:
- ✅ Happy path (it works)
- ✅ Edge cases (boundaries)
- ✅ Error cases (it fails gracefully)
- ✅ Security (it's safe)

**Test naming**: `should_result_when_condition`
