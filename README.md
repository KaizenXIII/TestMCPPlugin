# TestMCPPlugin

A minimal test harness for experimenting with MCP (Model Context Protocol) plugin behaviour using [Playwright](https://playwright.dev/) for end-to-end browser automation.

## Features

- Playwright-based end-to-end test setup, ready to extend
- Headless browser execution with a 1280x720 viewport configured out of the box
- Single example spec to validate the Playwright installation and serve as a starting point

## Prerequisites

- [Node.js](https://nodejs.org/) v16 or later (Playwright requires it)
- npm (bundled with Node.js)

## Installation

```bash
# Clone the repository
git clone <repository-url>
cd TestMCPPlugin

# Install dependencies
npm install

# Install Playwright browsers
npx playwright install
```

## Usage

Run all tests with the Playwright test runner:

```bash
npx playwright test
```

Run a specific spec file:

```bash
npx playwright test example.spec.js
```

Run tests in headed (visible browser) mode:

```bash
npx playwright test --headed
```

View the HTML test report after a run:

```bash
npx playwright show-report
```

## Project Structure

```
TestMCPPlugin/
├── playwright.config.js   # Playwright configuration (headless, viewport)
├── example.spec.js        # Sample test — navigates to playwright.dev and checks the page title
├── package-lock.json      # Dependency lockfile
└── README.md
```

### Key files

| File | Purpose |
|---|---|
| `playwright.config.js` | Global Playwright settings shared by all specs |
| `example.spec.js` | Starter test demonstrating `page.goto` and `expect(page).toHaveTitle` |

## Development

1. Add new spec files following the `*.spec.js` naming convention — Playwright picks them up automatically.
2. Extend `playwright.config.js` to configure additional projects (e.g. multiple browsers), base URLs, retries, or reporters.
3. There are currently no npm scripts defined. You can add convenience scripts to a `package.json`, for example:

```json
{
  "scripts": {
    "test": "playwright test",
    "test:headed": "playwright test --headed",
    "report": "playwright show-report"
  }
}
```

## License

No license file is present in this repository. All rights reserved unless otherwise stated.
