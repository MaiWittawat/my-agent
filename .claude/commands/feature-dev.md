# Feature Development

Plan and implement a new feature following project conventions.

## Input

$ARGUMENTS

## Process

### Step 1: Understand Requirements
- Clarify what the feature should do (ask if unclear)
- Identify acceptance criteria
- Determine scope — what's in and what's NOT in

### Step 2: Research Existing Code
- Find related code in the codebase
- Identify patterns already used for similar features
- Check for existing utilities/helpers that can be reused
- Note any constraints from current architecture

### Step 3: Plan Implementation
List the changes needed:
1. **Data layer** — new models, migrations, schema changes
2. **Business logic** — services, validators, transformations
3. **API layer** — new endpoints, request/response types
4. **UI layer** — components, pages, state (if applicable)
5. **Tests** — unit, integration, e2e as appropriate

### Step 4: Implement
- Follow existing project patterns and conventions
- Implement in order: data → logic → API → UI
- Add input validation at entry points
- Handle error cases explicitly
- Keep changes minimal — only what the feature requires

### Step 5: Test
- Write tests alongside implementation
- Cover happy path + key edge cases
- Run full test suite: `[TEST_COMMAND]`
- Run lint: `[LINT_COMMAND]`

### Step 6: Self-Review
- Re-read all changes as if reviewing someone else's code
- Check for leftover debug code, TODOs, console.logs
- Verify no secrets or sensitive data in code
- Confirm naming follows project conventions

## Rules
- DO NOT over-engineer. Build what was asked for, nothing more.
- DO NOT refactor unrelated code while implementing
- DO NOT add features beyond the stated requirements
- Follow existing patterns — don't invent new ones unless necessary
- If scope is unclear, ask before building
