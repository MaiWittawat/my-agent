# Plan Implementation

Create a detailed implementation plan before writing any code.

## Input

$ARGUMENTS

## Process

### Step 1: Define the Goal
- What problem are we solving?
- What does "done" look like?
- What are the constraints (time, tech, compatibility)?

### Step 2: Research
- Explore the current codebase for related code
- Identify existing patterns and conventions
- Check for libraries/tools already in use that apply
- Note any technical debt or limitations to work around

### Step 3: Design Options
For non-trivial tasks, outline 2-3 approaches:

| Approach | Pros | Cons | Effort |
|----------|------|------|--------|
| Option A | ... | ... | ... |
| Option B | ... | ... | ... |

Recommend one approach with clear reasoning.

### Step 4: Break Down Tasks

Create an ordered task list:

```
Phase 1: Foundation
  [ ] Task 1 — description (files affected)
  [ ] Task 2 — description (files affected)

Phase 2: Core Implementation
  [ ] Task 3 — description (files affected)
  [ ] Task 4 — description (files affected)

Phase 3: Testing & Polish
  [ ] Task 5 — description (files affected)
  [ ] Task 6 — description (files affected)
```

For each task, note:
- Files to create or modify
- Dependencies on other tasks
- Potential risks or unknowns

### Step 5: Identify Risks

| Risk | Impact | Mitigation |
|------|--------|------------|
| ... | ... | ... |

### Step 6: Define Checkpoints
- After which tasks should we pause and verify?
- What tests confirm each phase works?
- Where might we need to adjust the plan?

## Output

Deliver a plan with:
1. **Goal** — one-sentence summary
2. **Approach** — chosen design with reasoning
3. **Tasks** — ordered, with file paths and dependencies
4. **Risks** — what could go wrong and how to handle it
5. **Checkpoints** — when to verify progress

## Rules
- DO NOT write code during planning — plan first, build second
- Keep tasks small enough to verify independently
- Flag unknowns explicitly — don't hide uncertainty
- If requirements are ambiguous, list assumptions and ask for confirmation
- Prefer the simplest approach that meets the requirements
