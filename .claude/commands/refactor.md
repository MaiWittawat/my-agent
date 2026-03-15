# Safe Refactor

Refactor the specified code safely with pre/post verification.

## Input

$ARGUMENTS

## Process

### Step 1: Understand Current State
- Read the target code thoroughly
- Identify all callers and dependents (grep for usage)
- Run existing tests to establish a green baseline: `[TEST_COMMAND]`
- Note current behavior — this MUST NOT change

### Step 2: Assess Refactor Type

| Type | Risk | Approach |
|------|------|----------|
| Rename | Low | Find all references, rename in one pass |
| Extract function/method | Low | Extract, verify callers updated, test |
| Move file/module | Medium | Update all imports, check build |
| Change signature | Medium | Update all callers, verify types |
| Restructure logic | High | Small steps, test after each change |
| Change data model | High | Migration plan, backwards compat |

### Step 3: Pre-flight Checklist

Before making changes:
- [ ] All tests pass on current code
- [ ] Build succeeds: `[BUILD_COMMAND]`
- [ ] Lint passes: `[LINT_COMMAND]`
- [ ] I understand every caller of the code I'm changing
- [ ] I have a clear picture of what the code should look like after

### Step 4: Refactor — Small Steps

For each change:
1. Make ONE structural change
2. Run tests — must still pass
3. Run type check / build — must still pass
4. If anything breaks, FIX before continuing
5. Repeat

**DO NOT** batch multiple structural changes between test runs.

### Step 5: Post-flight Checklist

After all changes:
- [ ] All tests pass: `[TEST_COMMAND]`
- [ ] Build succeeds: `[BUILD_COMMAND]`
- [ ] Lint passes: `[LINT_COMMAND]`
- [ ] Type check passes: `[TYPECHECK_COMMAND]`
- [ ] No behavior change — only structure changed
- [ ] No dead code left behind (unused imports, functions, variables)
- [ ] No temporary compatibility shims remaining

### Step 6: Verify Behavior Preserved
- Run the same scenarios as before the refactor
- Compare outputs — must be identical
- If there are integration tests, run those too

## Rules
- Refactoring = changing structure WITHOUT changing behavior
- If you need to change behavior, that's a separate task — do it after
- NEVER refactor and add features in the same change
- NEVER skip tests between steps — that's how bugs sneak in
- If tests are missing for the code being refactored, write them FIRST
- Keep the diff reviewable — small, focused changes
- Delete dead code completely — no commented-out blocks or `_unused` vars
