# codeceptjs

Use CodeceptJS all-in-one installer (opens new window)to get CodeceptJS, a demo project, and Playwright.

## Install  codeceptjs
* Use CodeceptJS all-in-one installer (opens new window)to get CodeceptJS, a demo project, and Playwright.
```
mkdir myproject
cd myproject
npx create-codeceptjs .
```

* To start a new project initialize CodeceptJS to create main config file: codecept.conf.js.

```
npx codeceptjs init

```
? What helpers do you want to use?
❯◉ Playwright
 ◯ WebDriver
 ◯ Protractor
 ◯ Puppeteer
 ◯ Appium
 ◯ Nightmare
 ◯ FileSystem
 
 
** Write a simple test scenario:
```
Feature('My First Test');

Scenario('test something', ({ I }) => {
  I.amOnPage('https://github.com');
  I.see('GitHub');
});

```

** Run a test:
```
npm run codeceptjs
```

To see the step-by-step output of running tests, add the --steps flag:
```
npx codeceptjs run --steps
npx codeceptjs run --debug
```

To run all tests with the slow word in it:
```
npx codeceptjs run --grep "slow"
```
The output should be similar to this:

My First Test --
  test something
     I am on page "https://github.com"
     I see "GitHub"
 ✓ OK

## What's next  codeceptjs? 

* Try CodeceptJS now with a demo project:
➕ npm run codeceptjs:demo - executes codeceptjs tests for a demo project
➕ npm run codeceptjs:demo:headless - executes codeceptjs tests headlessly (no window shown)
➕ npm run codeceptjs:demo:ui - starts codeceptjs UI application for a demo project

* Initialize CodeceptJS for your project:
🔨 npx codeceptjs init - initialize codeceptjs for current project (required)
➕ npm run codeceptjs - runs codeceptjs tests for current project
➕ npm run codeceptjs:headless - executes codeceptjs tests headlessly (no window shown)
➕ npm run codeceptjs:ui - starts codeceptjs UI application for current project

## Videos codeceptjs

https://www.youtube.com/watch?v=7P99P5aNnz8

## Playwright ****

Installation#
Playwright has its own test runner for end-to-end tests, we call it Playwright Test.

```
mkdir myproject
cd myproject
npm i -D @playwright/test
 ** install supported browsers
npx playwright install
```

# First test#
Create tests/foo.spec.js (or tests/foo.spec.ts for TypeScript) to define your test.

* foo.spec.ts
```
const { test, expect } = require('@playwright/test');

test('basic test', async ({ page }) => {
  await page.goto('https://playwright.dev/');
  const title = page.locator('.navbar__inner .navbar__title');
  await expect(title).toHaveText('Playwright');
});
```

## Run Test 
* Run a single test file
```
npx playwright test tests/foo.spec.ts
```
* Run all file tests/*
```
npx playwright test --browser=firefox
```

# Generate code#
```
npx playwright codegen wikipedia.org
```

## Creating a configuration file:  playwright.config.js

```
// playwright.config.js
// @ts-check
const { devices } = require('@playwright/test');

/** @type {import('@playwright/test').PlaywrightTestConfig} */
const config = {
  projects: [
    {
      name: 'Desktop Chromium',
      use: {
        browserName: 'chromium',
        // Test against Chrome Beta channel.
        channel: 'chrome-beta',
      },
    },
    {
      name: 'Desktop Safari',
      use: {
        browserName: 'webkit',
        viewport: { width: 1200, height: 750 },
      }
    },
    // Test against mobile viewports.
    {
      name: 'Mobile Chrome',
      use: devices['Pixel 5'],
    },
    {
      name: 'Mobile Safari',
      use: devices['iPhone 12'],
    },
    {
      name: 'Desktop Firefox',
      use: {
        browserName: 'firefox',
        viewport: { width: 800, height: 600 },
      }
    },
  ],
};

module.exports = config;
```

##  Docs
- https://playwright.dev/docs/cli
- https://playwright.dev/docs/debug
- https://playwright.dev/docs/test-reporters
- https://playwright.dev/docs/input