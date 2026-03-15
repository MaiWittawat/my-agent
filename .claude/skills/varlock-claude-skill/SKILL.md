---
name: varlock
description: Secure environment variable management with Varlock. Use when handling secrets, API keys, credentials, or any sensitive configuration. Ensures secrets are never exposed in terminals, logs, traces, or Claude's context.
version: 1.0.0
---

# Varlock Security Skill

Secure-by-default environment variable management for Claude Code sessions.

> **Repository**: https://github.com/dmno-dev/varlock
> **Documentation**: https://varlock.dev

## Core Principle: Secrets Never Exposed

When working with Claude, secrets must NEVER appear in:
- Terminal output
- Claude's input/output context
- Log files or traces
- Git commits or diffs
- Error messages

---

## CRITICAL: Security Rules for Claude

### Rule 1: Never Echo Secrets

```bash
# ❌ NEVER DO THIS - exposes secret to Claude's context
echo $CLERK_SECRET_KEY
cat .env | grep SECRET
printenv | grep API

# ✅ DO THIS - validates without exposing
varlock load --quiet && echo "✓ Secrets validated"
```

### Rule 2: Never Read .env Directly

```bash
# ❌ NEVER DO THIS - exposes all secrets
cat .env
less .env
Read tool on .env file

# ✅ DO THIS - read schema (safe) not values
cat .env.schema
varlock load  # Shows masked values
```

### Rule 3: Use Varlock for Validation

```bash
# ❌ NEVER DO THIS - exposes secret in error
test -n "$API_KEY" && echo "Key: $API_KEY"

# ✅ DO THIS - Varlock validates and masks
varlock load
# Output shows: API_KEY 🔐sensitive └ ▒▒▒▒▒
```

### Rule 4: Never Include Secrets in Commands

```bash
# ❌ NEVER DO THIS - secret in command history
curl -H "Authorization: Bearer sk_live_xxx" https://api.example.com

# ✅ DO THIS - use environment variable
curl -H "Authorization: Bearer $API_KEY" https://api.example.com
# Or better: varlock run -- curl ...
```

---

## Quick Start

### Installation

```bash
# Install Varlock CLI
curl -sSfL https://varlock.dev/install.sh | sh -s -- --force-no-brew

# Add to PATH (add to ~/.zshrc or ~/.bashrc)
export PATH="$HOME/.varlock/bin:$PATH"

# Verify
varlock --version
```

### Initialize Project

```bash
# Create .env.schema from existing .env
varlock init

# Or create manually
touch .env.schema
```

---

## Schema File: .env.schema

### Basic Structure

```bash
# Global defaults
# @defaultSensitive=true @defaultRequired=infer

# Application
# @type=enum(development,staging,production) @sensitive=false
NODE_ENV=development

# @type=port @sensitive=false
PORT=3000

# Database - SENSITIVE
# @type=url @required
DATABASE_URL=

# @type=string @required @sensitive
DATABASE_PASSWORD=

# API Keys - SENSITIVE
# @type=string(startsWith=sk_) @required @sensitive
STRIPE_SECRET_KEY=

# @type=string(startsWith=pk_) @sensitive=false
STRIPE_PUBLISHABLE_KEY=
```

### Security Annotations

| Annotation | Effect | Use For |
|------------|--------|---------|
| `@sensitive` | Redacted in all output | API keys, passwords, tokens |
| `@sensitive=false` | Shown in logs | Public keys, non-secret config |
| `@defaultSensitive=true` | All vars sensitive by default | High-security projects |

### Type Annotations

| Type | Validates | Example |
|------|-----------|---------|
| `string` | Any string | `@type=string` |
| `string(startsWith=X)` | Prefix validation | `@type=string(startsWith=sk_)` |
| `url` | Valid URL | `@type=url` |
| `port` | 1-65535 | `@type=port` |
| `boolean` | true/false | `@type=boolean` |
| `enum(a,b,c)` | One of values | `@type=enum(dev,prod)` |

---

## Safe Commands for Claude

### Validating Environment

```bash
# Check all variables (safe - masks sensitive values)
varlock load

# Quiet mode (no output on success)
varlock load --quiet

# Check specific environment
varlock load --env=production
```

### Running Commands with Secrets

```bash
# Inject validated env into command
varlock run -- npm start
varlock run -- node script.js
varlock run -- pytest

# Secrets are available to the command but never printed
```

---

## Common Patterns

### Pattern 1: Validate Before Operations

```bash
# Always validate environment first
varlock load --quiet || {
  echo "❌ Environment validation failed"
  exit 1
}

# Then proceed with operation
npm run build
```

### Pattern 2: CI/CD Integration

```yaml
# GitHub Actions - secrets from GitHub Secrets
- name: Validate environment
  env:
    DATABASE_URL: ${{ secrets.DATABASE_URL }}
    API_KEY: ${{ secrets.API_KEY }}
  run: varlock load --quiet
```

### Pattern 3: Docker Integration

```dockerfile
# Install Varlock in container
RUN curl -sSfL https://varlock.dev/install.sh | sh -s -- --force-no-brew \
    && ln -s /root/.varlock/bin/varlock /usr/local/bin/varlock

# Validate at container start
CMD ["varlock", "run", "--", "npm", "start"]
```

---

## Handling Secret-Related Tasks

### When User Asks to "Check if API key is set"
```bash
# ✅ Safe approach
varlock load 2>&1 | grep "API_KEY"
# Shows: ✅ API_KEY 🔐sensitive └ ▒▒▒▒▒
```

### When User Asks to "Update a secret"
Claude should respond: "I cannot directly modify secrets for security reasons. Please update the value in your .env file manually or in your secrets manager, then run `varlock load` to validate."

### When User Asks to "Show me the .env file"
Claude should respond: "I won't read .env files directly as they contain secrets. Run `varlock load` to see masked values, or `cat .env.schema` to see the schema."

---

## Quick Reference Card

| Task | Safe Command |
|------|-------------|
| Validate all env vars | `varlock load` |
| Quiet validation | `varlock load --quiet` |
| Run with env | `varlock run -- <cmd>` |
| View schema | `cat .env.schema` |
| Check specific var | `varlock load \| grep VAR_NAME` |

| Never Do | Why |
|----------|-----|
| `cat .env` | Exposes all secrets |
| `echo $SECRET` | Exposes to Claude context |
| `printenv \| grep` | Exposes matching secrets |
| Read .env with tools | Secrets in Claude's context |
| Hardcode in commands | In shell history |

---

## Security Checklist for New Projects

- [ ] Install Varlock CLI
- [ ] Create `.env.schema` with all variables defined
- [ ] Mark all secrets with `@sensitive` annotation
- [ ] Add `@defaultSensitive=true` to schema header
- [ ] Add `.env` to `.gitignore`
- [ ] Commit `.env.schema` to version control
- [ ] Add `npm run env:validate` to CI/CD
- [ ] Document secret rotation procedure
- [ ] Never use `cat .env` or `echo $SECRET` in Claude sessions
