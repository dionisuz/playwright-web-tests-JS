# Playwright Web Tests (JS) — Automation QA Portfolio

Lightweight Playwright test suite demonstrating core web automation skills for an Automation QA portfolio: hooks, navigation, element checks, and context-level geolocation.

## Contents / Key Tests
- Hooks and page lifecycle (beforeAll, beforeEach, afterEach, afterAll)
- A/B Test page navigation & header verification
- Checkbox state verification
- Geolocation mocking via browser context and verification

## Tech Stack
- Node.js
- Playwright (JavaScript)
- Playwright Test runner
- Chromium (via Playwright)

## Prerequisites
- Node.js v16+ and npm
- Git (optional)

## Setup
1. Clone project
   - git clone <https://github.com/dionisuz/playwright-web-tests-JS>
2. Install dependencies
   - npm install
3. Install Playwright browsers
   - npx playwright install

## Run tests
- Run all tests:
  - npx playwright test
- Run a single file:
  - npx playwright test tests/hooksAndPage.spec.js
- Run a single test by name:
  - npx playwright test tests/hooksAndPage.spec.js -g "A/B Test"
- Run in headed mode:
  - npx playwright test --headed
- Open Inspector / debug:
  - npx playwright test --debug
- Run tests by tag:
  - npx playwright test --grep "@smoke"
  - npx playwright test --grep "@regression"
- Run using npm scripts:
  - npm run test:smoke (runs all tests tagged with @smoke)
  - npm run test:regression (runs all tests tagged with @regression)
  - npm run test:all (runs both smoke and regression tests)

## Test Results
Test results are generated in JSON format and saved to `test-results.json`. Reports include:
- Test status (passed, failed, skipped)
- Test duration and execution details
- Coverage of all test suites and specs

## Local test (selectors.spec.js)
The test `selectors.spec.js` uses a localhost URL that points to `clickMe.html`. Start a local server serving the project root before running this spec.

- VS Code Live Server: right-click `clickMe.html` → "Open with Live Server"
- Or run a simple static server from the project root:
  - npx http-server . -p 5500
  - python3 -m http.server 5500

Then open the page at the server URL (e.g. `http://127.0.0.1:5500/clickMe.html`) and run:
- npx playwright test tests/selectors.spec.js

## Notes
- page.pause() requires a visible inspector (use --debug or headed mode; headless prevents the interactive inspector).
- Geolocation is mocked by creating a new context with permissions and geolocation coordinates.

## Project structure
- tests/ — Playwright spec files (hooksAndPage.spec.js, selectors.spec.js)
- api_examples/ — API testing examples using Playwright's request context, includes:
  - tests/ — API spec files (api_examples.spec.js)
  - test-data/ — Static JSON data for response validation
  - playwright-report/ — HTML reports for API tests
  - test-results/ — API test run outputs
- pom_example/ — Page Object Model example demonstrating best practices for test organization
- package.json — scripts & dependencies
- README.md — this file

## Contact
- Portfolio owner: Denys Konoplov (see repo for contact links)