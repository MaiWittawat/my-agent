# Deploy Flow

Guide the deployment process for this project.

## Environments

| Environment | Branch       | URL                        | Auto-deploy |
|-------------|------------- |----------------------------|-------------|
| Development | `develop`    | [DEV_URL]                  | [yes/no]    |
| Staging     | `staging`    | [STAGING_URL]              | [yes/no]    |
| Production  | `main`       | [PROD_URL]                 | [yes/no]    |

## Pre-deploy Checklist

- [ ] All tests pass: `[TEST_COMMAND]`
- [ ] Lint passes: `[LINT_COMMAND]`
- [ ] Type check passes: `[TYPECHECK_COMMAND]`
- [ ] Build succeeds: `[BUILD_COMMAND]`
- [ ] No pending database migrations
- [ ] Environment variables are set in [ENV_MANAGEMENT_TOOL]
- [ ] [ADDITIONAL_CHECK_1]
- [ ] [ADDITIONAL_CHECK_2]

## Deploy Steps

### 1. Prepare
```bash
# Ensure on correct branch
git checkout [DEPLOY_BRANCH]
git pull origin [DEPLOY_BRANCH]

# Run all checks
[TEST_COMMAND]
[LINT_COMMAND]
[BUILD_COMMAND]
```

### 2. Database Migrations (if any)
```bash
[DB_MIGRATE_COMMAND]
# Verify: [DB_VERIFY_COMMAND]
```

### 3. Deploy
```bash
[DEPLOY_COMMAND]
# e.g. vercel --prod
# e.g. git push heroku main
# e.g. kubectl apply -f k8s/
# e.g. aws ecs update-service ...
```

### 4. Post-deploy Verification
```bash
# Health check
[HEALTH_CHECK_COMMAND]    # e.g. curl -s https://[PROD_URL]/health

# Smoke test
[SMOKE_TEST_COMMAND]      # e.g. npm run test:smoke
```

## Rollback Plan

```bash
# Option 1: Revert to previous version
[ROLLBACK_COMMAND]
# e.g. vercel rollback
# e.g. kubectl rollout undo deployment/[APP_NAME]

# Option 2: Revert commit and redeploy
git revert HEAD
git push origin [DEPLOY_BRANCH]
```

## Monitoring

- Logs: [LOG_DASHBOARD_URL]
- Metrics: [METRICS_DASHBOARD_URL]
- Alerts: [ALERTS_CHANNEL]
- Error tracking: [ERROR_TRACKING_URL]

## Instructions

When deploying:
1. Run through the pre-deploy checklist
2. Execute deploy steps in order
3. Verify deployment with health check
4. Monitor logs for 5 minutes after deploy
5. If issues found, execute rollback plan
