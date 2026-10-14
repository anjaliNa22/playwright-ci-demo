# Playwright End-to-End Test Suite 🎭

[![Playwright Tests](https://github.com/anjaliNa22/playwright-ci-demo/actions/workflows/playwright.yml/badge.svg)](https://github.com/anjaliNa22/playwright-ci-demo/actions/workflows/playwright.yml)

Automated end-to-end testing suite built with **Playwright** and **TypeScript**, automatically executed on every push and pull request via **GitHub Actions** CI/CD.

---

## 🚀 Features

- **Cross-Browser Testing**: Runs across Chromium, Firefox, and WebKit (Safari engine).
- **Headless CI Automation**: Fully automated pipeline on Ubuntu via GitHub Actions.
- **Artifact Archiving**: Automatically generates and uploads Playwright HTML reports on every run.
- **Trace & Screenshot Support**: Configured to capture failure diagnostics.

---

## 🛠️ Local Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/anjaliNa22/playwright-ci-demo.git
   cd playwright-ci-demo
   ```

2. **Install dependencies:**
   ```bash
   npm ci
   ```

3. **Install Playwright browsers:**
   ```bash
   npx playwright install --with-deps
   ```

4. **Run all tests:**
   ```bash
   npx playwright test
   ```

5. **View HTML test report:**
   ```bash
   npx playwright show-report
   ```

---

## ⚙️ CI/CD Workflow Architecture

The `.github/workflows/playwright.yml` pipeline runs on every `push` and `pull_request` targeting `main`:
1. **Checkout**: Retrieves source code via `actions/checkout@v4`.
2. **Environment Setup**: Provisions Node.js 20 with cached npm dependencies.
3. **Browser Provisioning**: Downloads browser binaries with necessary OS libraries (`--with-deps`).
4. **Test Execution**: Runs Playwright test suite in headless mode.
5. **Artifact Upload**: Uploads test results and HTML reports using `actions/upload-artifact@v4` with a 14-day retention period (runs even if tests fail).
