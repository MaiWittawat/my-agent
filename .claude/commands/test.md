# Write & Run Tests

Write tests for the specified code, then run them to verify.

## Input

$ARGUMENTS

## Process

### Step 1: Analyze the Code
- Read the target code thoroughly
- Identify all public functions/methods to test
- Map out code paths: happy path, edge cases, error cases
- Check existing tests for patterns and test utilities used

### Step 2: Plan Test Cases

For each function/endpoint, cover:

| Category | Examples |
|----------|----------|
| Happy path | Valid input → expected output |
| Edge cases | Empty input, null, zero, max values, boundary |
| Error cases | Invalid input, missing required fields, unauthorized |
| Integration | Component interactions, DB operations, API calls |

### Step 3: Write Tests

Follow project test conventions:
- Test framework: `[TEST_FRAMEWORK]`
- Test file location: `[TEST_DIR]`
- Naming pattern: `[TEST_FILE_PATTERN]`

Structure each test:
```
describe('[UnitName]', () => {
  describe('[methodName]', () => {
    it('should [expected behavior] when [condition]', () => {
      // Arrange — set up test data
      // Act — call the function
      // Assert — verify the result
    });
  });
});
```

### Step 4: Run Tests

```bash
# Run new tests only
[TEST_SINGLE_COMMAND]

# Run full suite to check for regressions
[TEST_COMMAND]
```

### Step 5: Verify Coverage
- All code paths are exercised
- No tests depend on execution order
- No hardcoded timeouts (use condition-based waiting)
- Tests are deterministic — same result every run

## Rules
- Tests should be independent — no shared mutable state
- Test behavior, not implementation details
- Use descriptive test names that explain the scenario
- DO NOT mock what you don't own (use fakes/stubs for external services)
- Keep tests fast — mock heavy I/O, use in-memory DB where possible
- One assertion concept per test (multiple asserts OK if testing same concept)
