# CLAUDE.md — Project Configuration

## Project Overview

- **Name:** [PROJECT_NAME]
- **Description:** [ONE_LINE_DESCRIPTION]
- **Type:** [web-app | api-service | cli-tool | library | monorepo]
- **Status:** [active | maintenance | archived]

## Tech Stack

- **Language:** [TypeScript | Go | Python | Rust | ...]
- **Runtime:** [Node.js 20 | Go 1.22 | Python 3.12 | ...]
- **Framework:** [Next.js 14 | Gin | FastAPI | ...]
- **Database:** [PostgreSQL | MySQL | MongoDB | ...]
- **ORM:** [Prisma | GORM | SQLAlchemy | ...]
- **Cache:** [Redis | Memcached | none]
- **Queue:** [BullMQ | RabbitMQ | SQS | none]
- **Auth:** [NextAuth | JWT | OAuth2 | ...]
- **Hosting:** [Vercel | AWS | GCP | self-hosted | ...]

## Commands

```bash
# Install dependencies
[INSTALL_COMMAND]            # e.g. npm install, go mod tidy

# Development
[DEV_COMMAND]                # e.g. npm run dev, go run ./cmd/server

# Build
[BUILD_COMMAND]              # e.g. npm run build, go build -o bin/server

# Test
[TEST_COMMAND]               # e.g. npm test, go test ./...
[TEST_SINGLE_COMMAND]        # e.g. npm test -- --grep "name", go test -run TestName

# Lint & Format
[LINT_COMMAND]               # e.g. npm run lint, golangci-lint run
[FORMAT_COMMAND]             # e.g. npm run format, gofmt -w .

# Database
[DB_MIGRATE_COMMAND]         # e.g. npx prisma migrate dev
[DB_SEED_COMMAND]            # e.g. npx prisma db seed

# Type check (if applicable)
[TYPECHECK_COMMAND]          # e.g. npx tsc --noEmit
```

## Project Structure

```
[PROJECT_ROOT]/
├── [SOURCE_DIR]/            # [e.g. src/, cmd/, app/]
│   ├── [ENTRY_POINT]        # [e.g. index.ts, main.go, app.py]
│   ├── [ROUTES_DIR]/        # [e.g. routes/, handlers/, api/]
│   ├── [MODELS_DIR]/        # [e.g. models/, entities/, schema/]
│   ├── [SERVICES_DIR]/      # [e.g. services/, usecases/]
│   └── [UTILS_DIR]/         # [e.g. utils/, pkg/, lib/]
├── [TEST_DIR]/              # [e.g. tests/, __tests__/, *_test.go]
├── [CONFIG_DIR]/            # [e.g. config/, .env.example]
└── [INFRA_DIR]/             # [e.g. infra/, deploy/, docker/]
```

## Coding Conventions

### Naming

- Files: [kebab-case | snake_case | camelCase]
- Functions: [camelCase | snake_case | PascalCase]
- Variables: [camelCase | snake_case]
- Constants: [UPPER_SNAKE_CASE | PascalCase]
- Types/Interfaces: [PascalCase] — [prefix with I | no prefix]
- Components: [PascalCase]

### Patterns

- Error handling: [return errors | throw exceptions | Result type]
- Async: [async/await | goroutines | promises]
- State management: [Zustand | Redux | Context | ...]
- API style: [REST | GraphQL | tRPC | gRPC]

### Rules

- [RULE_1]  # e.g. Always use named exports
- [RULE_2]  # e.g. No any types
- [RULE_3]  # e.g. All API endpoints must have validation
- [RULE_4]  # e.g. Keep functions under 50 lines

## Architecture Notes

[ARCHITECTURE_DESCRIPTION]

<!-- e.g.
- Hexagonal architecture with ports & adapters
- API layer -> Service layer -> Repository layer
- Events flow through BullMQ for async processing
- Auth middleware runs on all /api routes
-->

## Environment Variables

Required env vars (see `.env.example`):

- `[ENV_VAR_1]` — [description]
- `[ENV_VAR_2]` — [description]
- `[ENV_VAR_3]` — [description]

## External Services

- [SERVICE_1]: [purpose] — [dashboard/docs URL]
- [SERVICE_2]: [purpose] — [dashboard/docs URL]

---

## Available Commands

Slash commands available via `/command-name [args]`:

| Command | Description | When to Use |
|---------|-------------|-------------|
| `/debug [issue]` | Systematic root-cause debugging | Bug reports, test failures, unexpected behavior |
| `/code-review [file/PR]` | Review for correctness, security, performance | Before merging, after implementing |
| `/feature-dev [description]` | Plan and implement a new feature | Starting new feature work |
| `/test [target]` | Write and run tests for specified code | After implementing, missing coverage |
| `/plan [task]` | Create implementation plan before coding | Non-trivial tasks, architecture decisions |
| `/changelog [range]` | Generate changelog from git commits | Before releases, sprint summaries |
| `/refactor [target]` | Safe refactoring with pre/post verification | Restructuring code without behavior change |

### Project-Specific Commands

| Command | Description |
|---------|-------------|
| `/my-project/conventions` | Review code against project conventions |
| `/my-project/api-patterns` | Generate/review API endpoints using standard patterns |
| `/my-project/deploy` | Guide through deployment process |

## Available Skills

Skills are activated automatically when relevant context is detected.

| Skill | Trigger | Description |
|-------|---------|-------------|
| `systematic-debugging` | Debugging any technical issue | 4-phase process: investigate → analyze patterns → hypothesize → implement fix. Enforces root-cause investigation before any fix attempt. |
| `root-cause-tracing` | Bug deep in call stack, unclear data origin | Trace backward through call chain to find original trigger. Never fix at symptom point. |
| `owasp-security` | Writing auth, handling user input, crypto, API design | OWASP Top 10:2025 quick reference, security checklists, secure code patterns for 20+ languages, agentic AI security. |
| `varlock-claude-skill` | Handling secrets, .env files, API keys, credentials | Secure env var management. Prevents secrets from leaking into terminal, context, logs, or git. |
| `webapp-testing` | E2E testing, Playwright setup, UI test automation | Playwright patterns: Page Object Model, auth state, API mocking, locator strategies. |
| `tdd` | Building new features, fixing bugs with test-first | TDD cycle (RED→GREEN→REFACTOR), test patterns, testing doubles, outside-in TDD. |
| `my-stack` | [TRIGGER_CONDITIONS] | [PROJECT_SPECIFIC_SKILL — customize per project] |
