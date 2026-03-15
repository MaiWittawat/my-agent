# Generate Changelog

Generate a changelog from git commits for a specified range.

## Input

$ARGUMENTS

## Process

### Step 1: Determine Range
- If version/tag specified: use commits since that tag
- If no input: use commits since last tag or last 50 commits
- Run: `git log --oneline [range]` to preview

### Step 2: Categorize Commits

Parse each commit and categorize:

| Category | Prefix / Pattern | Example |
|----------|-----------------|---------|
| Features | `feat:`, `add:`, `new:` | New API endpoint, new component |
| Fixes | `fix:`, `bugfix:` | Bug fixes, corrections |
| Breaking | `breaking:`, `BREAKING CHANGE` | API changes, removed features |
| Performance | `perf:` | Optimizations, caching |
| Security | `security:`, `vuln:` | Security patches, dependency updates |
| Refactor | `refactor:` | Code restructuring (no behavior change) |
| Docs | `docs:` | Documentation updates |
| Chore | `chore:`, `ci:`, `build:` | Dependencies, CI, tooling |

### Step 3: Generate Changelog

Format as:

```markdown
## [VERSION] — YYYY-MM-DD

### Breaking Changes
- description (#PR)

### Features
- description (#PR)

### Fixes
- description (#PR)

### Performance
- description (#PR)

### Security
- description (#PR)
```

### Step 4: Review
- Verify no commits were missed
- Ensure descriptions are user-facing (not internal jargon)
- Highlight breaking changes prominently
- Link to PRs/issues where available

## Rules
- Write for end users, not developers (unless internal changelog)
- Group related commits into single entries
- Skip merge commits and trivial chores unless relevant
- Always put breaking changes first
- Use past tense: "Added...", "Fixed...", "Removed..."
- If commit messages are poor, read the diffs to write better descriptions
