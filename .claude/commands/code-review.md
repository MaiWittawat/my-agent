# Code Review

Review the specified code for correctness, security, performance, and maintainability.

## Input

$ARGUMENTS

## Review Checklist

### 1. Correctness
- [ ] Logic handles all edge cases (null, empty, boundary values)
- [ ] Error handling is complete — no silent failures
- [ ] Async operations are properly awaited
- [ ] Return types match expected values
- [ ] No off-by-one errors or incorrect comparisons

### 2. Security (OWASP)
- [ ] User input is validated and sanitized
- [ ] No SQL injection (parameterized queries used)
- [ ] No command injection (no shell=True with user input)
- [ ] No hardcoded secrets or credentials
- [ ] Auth/authz checks are present where needed
- [ ] Errors don't expose internal details to users
- [ ] Fail-closed on errors (deny, not allow)

### 3. Performance
- [ ] No N+1 queries or unnecessary DB calls
- [ ] No expensive operations inside loops
- [ ] Proper indexing for queried fields
- [ ] Large datasets are paginated
- [ ] No memory leaks (event listeners cleaned up, connections closed)

### 4. Maintainability
- [ ] Functions are focused (single responsibility)
- [ ] Naming is clear and consistent with codebase conventions
- [ ] No duplicated logic that should be shared
- [ ] Complex logic has explanatory comments
- [ ] No dead code or unused imports

### 5. Testing
- [ ] New code paths have corresponding tests
- [ ] Edge cases are tested
- [ ] Tests are deterministic (no flaky timing dependencies)

## Output Format

For each issue found:
```
[SEVERITY] file:line — description
  → suggested fix
```

Severity levels:
- **CRITICAL** — Security vulnerability or data loss risk
- **BUG** — Will cause incorrect behavior
- **WARN** — Potential issue or code smell
- **NIT** — Style or minor improvement

End with a summary: total issues by severity, overall assessment (approve / request changes).
