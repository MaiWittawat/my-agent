# Test-Driven Development (TDD)

## When to Use

Activate this skill when:
- Building new features from scratch
- Fixing a bug (write failing test first, then fix)
- Refactoring code that lacks test coverage
- User explicitly asks for TDD approach
- Implementing business logic with clear input/output

## The TDD Cycle

```
RED → GREEN → REFACTOR → repeat
```

### 1. RED — Write a Failing Test

Write the **smallest** test that describes the next piece of behavior.

```typescript
// Start with the simplest case
test('adds two numbers', () => {
  expect(add(1, 2)).toBe(3);
});
```

**Rules:**
- Test MUST fail before you write implementation
- Test MUST fail for the RIGHT reason (not syntax error)
- Write only ONE test at a time
- Test describes behavior, not implementation

### 2. GREEN — Make It Pass

Write the **minimum** code to make the test pass.

```typescript
function add(a: number, b: number): number {
  return a + b;
}
```

**Rules:**
- Write the simplest possible implementation
- It's OK to hardcode or use naive solutions
- Do NOT write more code than needed to pass the test
- Do NOT add edge case handling you haven't tested yet
- Run the test — it MUST pass

### 3. REFACTOR — Clean Up

Improve the code while keeping all tests green.

**Rules:**
- Run tests after EVERY change
- Remove duplication
- Improve naming
- Extract functions if needed
- Do NOT add new behavior during refactor
- If tests break, undo and try smaller change

## TDD Patterns

### Pattern 1: Triangulation

Start simple, add tests to force generalization:

```typescript
// Test 1 — could hardcode
test('greet returns hello message', () => {
  expect(greet('World')).toBe('Hello, World!');
});

// Test 2 — forces real implementation
test('greet with different name', () => {
  expect(greet('Alice')).toBe('Hello, Alice!');
});
```

### Pattern 2: Edge Cases Drive Design

Let edge cases reveal design decisions:

```typescript
// Happy path first
test('divides two numbers', () => {
  expect(divide(10, 2)).toBe(5);
});

// Edge case drives error handling
test('throws on division by zero', () => {
  expect(() => divide(10, 0)).toThrow('Cannot divide by zero');
});

// Edge case drives type handling
test('handles decimal results', () => {
  expect(divide(7, 2)).toBe(3.5);
});
```

### Pattern 3: Outside-In TDD

Start from the API/handler, work inward:

```
1. Write E2E/integration test for endpoint → FAIL
2. Write handler that calls service → needs service
3. Write unit test for service → FAIL
4. Implement service that calls repository → needs repo
5. Write unit test for repository → FAIL
6. Implement repository
7. All tests GREEN from inside out
```

### Pattern 4: Test List

Before coding, brainstorm test cases:

```
Feature: User Registration
- [ ] Valid email and password creates user
- [ ] Duplicate email returns 409
- [ ] Invalid email format returns 400
- [ ] Password too short returns 400
- [ ] Missing required fields returns 400
- [ ] Successful registration sends welcome email
- [ ] Password is hashed before storing
```

Work through the list one test at a time.

## Test Quality Checklist

### Good Test Characteristics
- [ ] **Fast** — runs in milliseconds
- [ ] **Isolated** — no dependency on other tests
- [ ] **Repeatable** — same result every time
- [ ] **Self-validating** — pass/fail without manual checking
- [ ] **Timely** — written before or alongside code

### Test Naming Convention

```
[unit]_[scenario]_[expectedResult]

// Examples:
test('createUser_withValidData_returnsNewUser')
test('createUser_withDuplicateEmail_throwsConflictError')
test('calculateTotal_withEmptyCart_returnsZero')
```

Or BDD style:
```
describe('[Unit]', () => {
  describe('[method]', () => {
    it('should [expected] when [condition]')
  })
})
```

## Arrange-Act-Assert

Every test follows this structure:

```typescript
test('applies discount to order total', () => {
  // Arrange — set up preconditions
  const order = createOrder({ items: [{ price: 100, qty: 2 }] });
  const discount = { type: 'percentage', value: 10 };

  // Act — perform the action
  const result = applyDiscount(order, discount);

  // Assert — verify the outcome
  expect(result.total).toBe(180);
  expect(result.discountApplied).toBe(20);
});
```

## Testing Doubles

| Type | Purpose | Example |
|------|---------|---------|
| Stub | Return canned data | `jest.fn().mockReturnValue(42)` |
| Spy | Verify interaction | `jest.spyOn(service, 'save')` |
| Fake | Working simplified implementation | In-memory database |
| Mock | Stub + assertion on calls | `expect(mock).toHaveBeenCalledWith(...)` |

### When to Use What

```
External API → Stub (return fake data)
Database → Fake (in-memory) or real (integration test)
Logger → Spy (verify it was called)
Email service → Mock (verify correct email sent)
```

## Common TDD Mistakes

| Mistake | Problem | Fix |
|---------|---------|-----|
| Writing too many tests at once | Lose focus, skip RED step | One test at a time |
| Testing implementation details | Tests break on refactor | Test behavior and outputs |
| Making too big a leap | Hard to debug failures | Smaller steps |
| Skipping refactor step | Code quality degrades | Always clean up after GREEN |
| Over-mocking | Tests don't catch real bugs | Prefer fakes, test integration |
| Testing getters/setters | No value, adds maintenance | Test meaningful behavior |

## Do's and Don'ts

### Do
- Write the test BEFORE the implementation
- Keep tests small — one concept per test
- Run ALL tests after every change
- Use descriptive test names that read like documentation
- Delete tests that no longer add value
- Let failing tests guide your implementation

### Don't
- Don't write implementation first then "backfill" tests
- Don't skip the RED step — if the test passes immediately, it tests nothing
- Don't test private methods directly — test through public API
- Don't mock what you don't own — wrap external libs, mock the wrapper
- Don't ignore the refactor step — it's what keeps TDD sustainable
- Don't write tests for trivial code (simple getters, constants)
