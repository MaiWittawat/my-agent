# Web App Testing with Playwright

## When to Use

Activate this skill when:
- Writing or running end-to-end (E2E) tests for web applications
- Testing user flows, forms, navigation, or UI interactions
- Setting up Playwright in a new project
- Debugging flaky E2E tests
- Testing across multiple browsers

## Setup

```bash
# Install
npm init playwright@latest

# Or add to existing project
npm install -D @playwright/test
npx playwright install
```

### Config Template

```typescript
// playwright.config.ts
import { defineConfig, devices } from '@playwright/test';

export default defineConfig({
  testDir: './e2e',
  fullyParallel: true,
  forbidOnly: !!process.env.CI,
  retries: process.env.CI ? 2 : 0,
  workers: process.env.CI ? 1 : undefined,
  reporter: process.env.CI ? 'github' : 'html',
  use: {
    baseURL: 'http://localhost:3000',
    trace: 'on-first-retry',
    screenshot: 'only-on-failure',
  },
  projects: [
    { name: 'chromium', use: { ...devices['Desktop Chrome'] } },
    { name: 'firefox', use: { ...devices['Desktop Firefox'] } },
    { name: 'mobile', use: { ...devices['iPhone 14'] } },
  ],
  webServer: {
    command: 'npm run dev',
    url: 'http://localhost:3000',
    reuseExistingServer: !process.env.CI,
  },
});
```

## Core Patterns

### Page Object Model

```typescript
// e2e/pages/login.page.ts
import { type Page, type Locator } from '@playwright/test';

export class LoginPage {
  readonly emailInput: Locator;
  readonly passwordInput: Locator;
  readonly submitButton: Locator;
  readonly errorMessage: Locator;

  constructor(private page: Page) {
    this.emailInput = page.getByLabel('Email');
    this.passwordInput = page.getByLabel('Password');
    this.submitButton = page.getByRole('button', { name: 'Sign in' });
    this.errorMessage = page.getByRole('alert');
  }

  async goto() {
    await this.page.goto('/login');
  }

  async login(email: string, password: string) {
    await this.emailInput.fill(email);
    await this.passwordInput.fill(password);
    await this.submitButton.click();
  }
}
```

### Test Structure

```typescript
// e2e/auth.spec.ts
import { test, expect } from '@playwright/test';
import { LoginPage } from './pages/login.page';

test.describe('Authentication', () => {
  let loginPage: LoginPage;

  test.beforeEach(async ({ page }) => {
    loginPage = new LoginPage(page);
    await loginPage.goto();
  });

  test('successful login redirects to dashboard', async ({ page }) => {
    await loginPage.login('user@test.com', 'password123');
    await expect(page).toHaveURL('/dashboard');
    await expect(page.getByText('Welcome')).toBeVisible();
  });

  test('invalid credentials shows error', async () => {
    await loginPage.login('bad@test.com', 'wrong');
    await expect(loginPage.errorMessage).toHaveText('Invalid credentials');
  });
});
```

### API Mocking

```typescript
test('displays data from API', async ({ page }) => {
  // Mock API response
  await page.route('**/api/users', async (route) => {
    await route.fulfill({
      status: 200,
      contentType: 'application/json',
      body: JSON.stringify([
        { id: 1, name: 'Test User' },
      ]),
    });
  });

  await page.goto('/users');
  await expect(page.getByText('Test User')).toBeVisible();
});
```

### Authentication State

```typescript
// e2e/auth.setup.ts
import { test as setup, expect } from '@playwright/test';

const authFile = 'e2e/.auth/user.json';

setup('authenticate', async ({ page }) => {
  await page.goto('/login');
  await page.getByLabel('Email').fill('test@example.com');
  await page.getByLabel('Password').fill('password');
  await page.getByRole('button', { name: 'Sign in' }).click();
  await page.waitForURL('/dashboard');
  await page.context().storageState({ path: authFile });
});

// In playwright.config.ts, add:
// { name: 'setup', testMatch: /.*\.setup\.ts/ },
// { name: 'tests', dependencies: ['setup'], use: { storageState: authFile } },
```

## Locator Strategy (Priority Order)

| Priority | Locator | Example | When |
|----------|---------|---------|------|
| 1 | getByRole | `getByRole('button', { name: 'Submit' })` | Always prefer |
| 2 | getByLabel | `getByLabel('Email')` | Form fields |
| 3 | getByText | `getByText('Welcome')` | Text content |
| 4 | getByTestId | `getByTestId('nav-menu')` | No semantic option |
| 5 | CSS/XPath | `locator('.class')` | Last resort |

## Assertions

```typescript
// Visibility
await expect(locator).toBeVisible();
await expect(locator).toBeHidden();

// Text
await expect(locator).toHaveText('exact text');
await expect(locator).toContainText('partial');

// Input
await expect(locator).toHaveValue('input value');
await expect(locator).toBeChecked();
await expect(locator).toBeDisabled();

// Page
await expect(page).toHaveURL('/expected-path');
await expect(page).toHaveTitle('Page Title');

// Count
await expect(page.getByRole('listitem')).toHaveCount(3);

// Screenshot comparison
await expect(page).toHaveScreenshot('homepage.png');
```

## Handling Common Scenarios

### Wait for Navigation
```typescript
await Promise.all([
  page.waitForURL('/next-page'),
  page.getByRole('link', { name: 'Next' }).click(),
]);
```

### File Upload
```typescript
const fileInput = page.getByLabel('Upload file');
await fileInput.setInputFiles('path/to/file.pdf');
```

### Dialogs
```typescript
page.on('dialog', dialog => dialog.accept());
await page.getByRole('button', { name: 'Delete' }).click();
```

### iframes
```typescript
const frame = page.frameLocator('#payment-iframe');
await frame.getByLabel('Card number').fill('4242424242424242');
```

## Commands

```bash
# Run all tests
npx playwright test

# Run specific file
npx playwright test e2e/auth.spec.ts

# Run in headed mode (see browser)
npx playwright test --headed

# Run specific browser
npx playwright test --project=chromium

# Debug mode (step through)
npx playwright test --debug

# Generate test from actions
npx playwright codegen localhost:3000

# View report
npx playwright show-report
```

## Do's and Don'ts

### Do
- Use role-based locators (`getByRole`, `getByLabel`) over CSS selectors
- Use Page Object Model for reusable pages
- Set up auth state once in setup, reuse via `storageState`
- Use `expect` auto-waiting — don't add manual waits
- Run tests in CI with retries enabled
- Use `test.describe` to group related tests

### Don't
- Don't use `page.waitForTimeout()` — use `expect` auto-wait instead
- Don't use CSS class selectors — they break on style changes
- Don't share state between tests — each test should be independent
- Don't test third-party UI (payment forms, OAuth popups) — mock them
- Don't use `page.evaluate` unless absolutely necessary
- Don't hardcode test data — use fixtures or factories
