# Debug Issue

Systematically debug the reported issue following root-cause analysis.

## Input

$ARGUMENTS

## Process

### Step 1: Understand the Problem
- Read the error message / stack trace carefully
- Identify the affected file(s) and line number(s)
- Determine if this is a runtime error, build error, or logic bug

### Step 2: Reproduce
- Find or create the minimal reproduction steps
- Confirm the issue exists in the current codebase
- Check `git log --oneline -10` for recent changes that may have caused it

### Step 3: Root Cause Investigation
- Trace the data flow backward from where the error occurs
- Check each function in the call chain for incorrect values
- Log key variables at component boundaries if needed
- Identify the ORIGINAL source of the bad data/behavior

### Step 4: Fix
- Fix at the root cause, not at the symptom
- Make the SMALLEST possible change
- Add validation at entry points to prevent recurrence

### Step 5: Verify
- Run the failing test/scenario to confirm the fix
- Run the full test suite to check for regressions: `[TEST_COMMAND]`
- Verify no other code paths are affected

## Rules
- DO NOT guess-and-check. Investigate first, fix second.
- DO NOT fix multiple things at once
- If 3+ fix attempts fail, stop and reassess the architecture
- Always explain what the root cause was
