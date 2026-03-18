# AXEDemo

[![Pa11y Accessibility Check](https://github.com/Mitesh411/AXEDemo/actions/workflows/blank.yml/badge.svg)](https://github.com/Mitesh411/AXEDemo/actions/workflows/blank.yml)

AXEDemo is a repository demonstrating automated web accessibility testing using [pa11y-ci](https://github.com/pa11y/pa11y-ci). It evaluates remote URLs and local components against WCAG standards to ensure web interfaces are accessible to all users.

## Features

- **Automated Testing:** Runs comprehensive accessibility checks against targeted web pages.
- **WCAG 2.0 AA Compliance:** Configured by default to test against strict WCAG2AA standards.
- **CI/CD Integration:** Includes GitHub Actions workflows to continuously run tests on pushes and pull requests.
- **Artifact Generation:** Automatically generates and uploads JSON reports summarizing accessibility issues on every CI run.

## Prerequisites

Ensure you have the following installed on your local machine:

- **Node.js:** `>=22.0.0`
- **npm:** Typically included with Node.js installation.

## Installation

Clone the repository and install the required dependencies:

```bash
git clone https://github.com/Mitesh411/AXEDemo.git
cd AXEDemo
npm install
```

## Usage

To run the accessibility checks locally, follow these steps:

1. **Start the local server** (if evaluating local files):
   ```bash
   npm run start
   ```
   *This runs `http-server` locally on port `8080`.*

2. **Run the Accessibility Tests:**
   ```bash
   npm run a11y
   ```
   *This executes `pa11y-ci` against the URLs defined in your configuration file.*

## Configuration

Accessibility rules, timeouts, and target URLs are managed within the `.pa11yci` configuration file.

- **Standard:** Enforces `WCAG2AA`.
- **Ignored Rules:** Specific rules can be bypassed via the `ignore` array to accommodate intentional design decisions or false positives.
- **Target URLs:** Specifies the remote URLs or local paths to be evaluated (currently configured for a portfolio resume page).

## Continuous Integration

This project utilizes **GitHub Actions** for continuous integration. The workflow defined in `.github/workflows/blank.yml` triggers automatically on:

- Pushes to the `main` branch.
- Pull requests targeting the `main` branch.

**Workflow Pipeline:**
1. Checks out the repository.
2. Sets up the Node.js (v22) environment.
3. Installs project dependencies.
4. Starts the local server in the background.
5. Executes `pa11y-ci` and exports the results to `pa11y-report.json`.
6. Uploads the generated `pa11y-report.json` as an artifact for post-run analysis.

## Tooling Versions

- Node.js: `>=22`
- pa11y-ci: `^4.0.1`
- http-server: `^14.1.1`
