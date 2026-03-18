# AXEDemo

A professional, automated accessibility testing suite leveraging **pa11y-ci**. This project simplifies validating web interfaces against WCAG 2.0 AA standards, ensuring digital content is accessible to all users.

Currently, the suite is configured to run accessibility checks against a live, remote portfolio/resume site.

## 🚀 Features

* **Automated Accessibility Testing:** Uses `pa11y-ci` to quickly scan URLs for accessibility violations.
* **WCAG 2.0 AA Compliance:** Configured by default to target the standard WCAG2AA ruleset.
* **Custom Rule Ignore List:** Easily suppress known or irrelevant errors via the `.pa11yci` configuration file.
* **Headless Browser Execution:** Leverages Puppeteer/Chrome under the hood for reliable DOM rendering and testing.
* **CI/CD Ready:** Built to be easily integrated into any Continuous Integration pipeline.

## 🛠️ Prerequisites

Ensure you have the following installed on your local machine:

* **Node.js:** `>= 22.0.0`
* **npm** (comes with Node.js)

## 📦 Installation

1. **Clone the repository:**
   ```bash
   git clone <repository-url>
   cd AXEDemo
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```
   *This will install the required dev dependencies: `pa11y-ci` and `http-server`.*

## ⚙️ Configuration

The accessibility checks are controlled by the `.pa11yci` file located in the project root.

### Key configurations:
* **Standard:** `WCAG2AA`
* **Target URLs:** Currently configured to test `https://mitesh411.github.io/MyResume/`.
* **Ignored Rules:** Several specific WCAG errors (such as missing titles, empty links, or contrast issues in specific contexts) are currently ignored to reduce noise. You can modify the `ignore` array in `.pa11yci` to suit your needs.

## 💻 Usage

### Running Accessibility Tests

To execute the accessibility scan against the configured URLs:

```bash
npm run a11y
```

This command runs `pa11y-ci` which will output a report in your terminal detailing any accessibility errors found on the target pages.

### Local Server (Optional)

If you need to serve local files to test them (e.g., if you change the target URL in `.pa11yci` to point to a local directory):

```bash
npm run start
```

This will start an `http-server` on `http://localhost:8080`.

## 📂 Project Structure

```
AXEDemo/
├── .pa11yci          # pa11y-ci configuration file (rules, URLs, ignores)
├── package.json      # Project metadata and npm scripts
├── package-lock.json # Exact dependency tree
└── README.md         # Project documentation (this file)
```
