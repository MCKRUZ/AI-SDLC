# Testing Pyramid Reference

## Overview

The testing pyramid guides test distribution across different levels,
optimizing for fast feedback and comprehensive coverage.

---

## The Pyramid

```
         /\
        /  \        E2E Tests (10%)
       /    \       Slow, expensive, few
      /──────\
     /        \     Integration Tests (20%)
    /          \    Medium speed, moderate count
   /────────────\
  /              \  Unit Tests (70%)
 /                \ Fast, cheap, many
/──────────────────\
```

---

## Test Levels

### Unit Tests (70%)

**What**: Test individual functions/methods in isolation.

| Aspect | Guideline |
|--------|-----------|
| Scope | Single function/class |
| Dependencies | Mocked/stubbed |
| Speed | Milliseconds |
| Count | Hundreds to thousands |
| Maintained by | Developers |

**Characteristics**:
- Fast execution (< 10ms each)
- No external dependencies
- Deterministic (no flakiness)
- Easy to write and maintain

**Example**:
```javascript
test('calculateTotal adds items correctly', () => {
  const cart = new Cart();
  cart.add({ price: 10, qty: 2 });
  cart.add({ price: 5, qty: 1 });
  expect(cart.total()).toBe(25);
});
```

### Integration Tests (20%)

**What**: Test interactions between components.

| Aspect | Guideline |
|--------|-----------|
| Scope | Multiple components |
| Dependencies | Real or test doubles |
| Speed | Seconds |
| Count | Dozens to hundreds |
| Maintained by | Developers |

**Characteristics**:
- Test component boundaries
- May use test databases
- Verify contracts between services
- Slower than unit tests

**Example**:
```javascript
test('UserService creates user in database', async () => {
  const user = await userService.create({ email: 'test@example.com' });
  const found = await db.users.findById(user.id);
  expect(found.email).toBe('test@example.com');
});
```

### End-to-End Tests (10%)

**What**: Test complete user flows through the system.

| Aspect | Guideline |
|--------|-----------|
| Scope | Full system |
| Dependencies | Real services |
| Speed | Minutes |
| Count | Tens |
| Maintained by | QA + Developers |

**Characteristics**:
- Test real user scenarios
- Use production-like environment
- Most expensive to run
- Most prone to flakiness

**Example**:
```javascript
test('user can complete checkout', async () => {
  await page.goto('/products');
  await page.click('[data-testid="product-1"]');
  await page.click('[data-testid="add-to-cart"]');
  await page.goto('/checkout');
  await page.fill('#email', 'test@example.com');
  await page.click('#submit');
  await expect(page).toHaveURL('/confirmation');
});
```

---

## Additional Test Types

### Contract Tests

Verify API contracts between services.

```javascript
test('user API returns expected schema', async () => {
  const response = await api.get('/users/1');
  expect(response).toMatchSchema(userSchema);
});
```

### Performance Tests

Verify system meets performance requirements.

| Type | What | When |
|------|------|------|
| Load | Normal traffic | Pre-release |
| Stress | Beyond capacity | Pre-release |
| Endurance | Extended duration | Periodically |

### Security Tests

| Type | Tool Examples |
|------|---------------|
| SAST | SonarQube, CodeQL |
| DAST | OWASP ZAP, Burp |
| Dependency | Snyk, Dependabot |

---

## Coverage Guidelines

### Recommended Targets

| Level | Coverage Target |
|-------|-----------------|
| Unit | 80%+ line coverage |
| Integration | Critical paths covered |
| E2E | Happy paths + key edge cases |

### What to Cover

**Unit Tests**:
- Business logic
- Calculations
- Validations
- Edge cases
- Error handling

**Integration Tests**:
- Database operations
- API endpoints
- External service calls
- Authentication flows

**E2E Tests**:
- Critical user journeys
- Payment flows
- Sign-up/sign-in
- Main feature workflows

### What NOT to Test

- Trivial getters/setters
- Framework code
- Third-party libraries
- Declarative configuration

---

## Test Quality

### Good Test Characteristics (F.I.R.S.T.)

| Principle | Meaning |
|-----------|---------|
| **F**ast | Run quickly |
| **I**ndependent | No test order dependencies |
| **R**epeatable | Same result every time |
| **S**elf-validating | Pass or fail clearly |
| **T**imely | Written with code |

### Test Smells to Avoid

| Smell | Problem | Solution |
|-------|---------|----------|
| Flaky tests | Inconsistent results | Fix or delete |
| Slow tests | Delayed feedback | Move down pyramid |
| Coupled tests | Order-dependent | Isolate properly |
| Commented tests | Dead code | Delete or fix |

---

## CI/CD Integration

### Test Execution Order

```
1. Unit Tests        (every commit)    < 2 min
2. Integration Tests (every commit)    < 5 min
3. E2E Tests         (pre-merge)       < 15 min
4. Performance Tests (nightly/release) variable
```

### Quality Gates

| Gate | Criteria |
|------|----------|
| PR Merge | Unit + Integration pass, coverage ≥ X% |
| Staging Deploy | All tests pass |
| Production Deploy | All tests pass + manual approval |

---

## Quick Reference

**Pyramid Balance**:
- 70% Unit (fast, many)
- 20% Integration (medium)
- 10% E2E (slow, few)

**When adding tests**:
1. Start with unit tests
2. Add integration for boundaries
3. Add E2E for critical paths only
