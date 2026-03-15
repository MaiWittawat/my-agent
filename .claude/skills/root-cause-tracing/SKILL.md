# Root Cause Tracing

## Overview

Bugs often manifest deep in the call stack (git init in wrong directory, file created in wrong location, database opened with wrong path). Your instinct is to fix where the error appears, but that's treating a symptom.

**Core principle:** Trace backward through the call chain until you find the original trigger, then fix at the source.

## When to Use

**Use when:**
- Error happens deep in execution (not at entry point)
- Stack trace shows long call chain
- Unclear where invalid data originated
- Need to find which test/code triggers the problem

## The Tracing Process

### 1. Observe the Symptom
```
Error: git init failed in /Users/jesse/project/packages/core
```

### 2. Find Immediate Cause
**What code directly causes this?**
```typescript
await execFileAsync('git', ['init'], { cwd: projectDir });
```

### 3. Ask: What Called This?
```typescript
WorktreeManager.createSessionWorktree(projectDir, sessionId)
  → called by Session.initializeWorkspace()
  → called by Session.create()
  → called by test at Project.create()
```

### 4. Keep Tracing Up
**What value was passed?**
- `projectDir = ''` (empty string!)
- Empty string as `cwd` resolves to `process.cwd()`
- That's the source code directory!

### 5. Find Original Trigger
**Where did empty string come from?**
```typescript
const context = setupCoreTest(); // Returns { tempDir: '' }
Project.create('name', context.tempDir); // Accessed before beforeEach!
```

## Adding Stack Traces

When you can't trace manually, add instrumentation:

```typescript
async function gitInit(directory: string) {
  const stack = new Error().stack;
  console.error('DEBUG git init:', {
    directory,
    cwd: process.cwd(),
    nodeEnv: process.env.NODE_ENV,
    stack,
  });
  await execFileAsync('git', ['init'], { cwd: directory });
}
```

**Critical:** Use `console.error()` in tests (not logger - may not show)

## Finding Which Test Causes Pollution

If something appears during tests but you don't know which test, use bisection:

```bash
# Run tests one-by-one, check for pollution after each
for test_file in src/**/*.test.ts; do
  npx jest "$test_file" --forceExit
  if [ -e ".git/pollution-marker" ]; then
    echo "POLLUTER: $test_file"
    break
  fi
done
```

## Key Principles

1. **NEVER fix just where the error appears** — trace back to the original trigger
2. **Use `console.error()` in tests** — logger may be suppressed
3. **Log before the dangerous operation** — not after it fails
4. **Include context** — directory, cwd, environment variables, timestamps
5. **Capture stack** — `new Error().stack` shows complete call chain

## After Finding Root Cause

Once you've traced to the source:

1. **Fix at the source** — not at the symptom point
2. **Add defense-in-depth** — validate at every layer the data passes through
3. **Add a test** — reproduce the original bug, verify the fix
4. **Add instrumentation** — make future tracing easier

## Quick Reference

| Step | Action | Question |
|------|--------|----------|
| 1 | Observe symptom | What error/behavior do I see? |
| 2 | Find immediate cause | What code directly causes this? |
| 3 | Trace caller | What called this function? |
| 4 | Check values | What values were passed? |
| 5 | Keep tracing | Where did those values come from? |
| 6 | Find trigger | What is the original source? |
| 7 | Fix at source | How do I fix the root cause? |
