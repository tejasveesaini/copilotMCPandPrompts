This repository contains prompt template, showing the best practices to create effective prompts for GitHub Copilot MCP agents. Prompt template can be tried without the github mcp server as well.

Notes:
1. Make the prompts part of shared repository.
Add your central prompt repo as a Git Submodule inside the .github directory of your main projects. This keeps the templates in a single central repo, but "projects" them into every other repo. When you update the central repo, you just update the submodule reference.

2. Community-contributed instructions, prompts, and configurations to help you make the most of GitHub Copilot:
https://github.com/github/awesome-copilot?tab=readme-ov-file#-custom-instructions


## Output from [Prompt projectInfo.prompt.md](.github/prompts/projectInfo.prompt.md)

(In the github copilot, entered /projectinfo)

**tejasveesaini**: Follow instructions in [projectInfo.prompt.md](file:///Users/tejasveesaini/vs%20code%20projects/copilotMCPandPrompts/.github/prompts/projectInfo.prompt.md).

(Checked if it asks for the variable defined in the prompt)

**GitHub Copilot**: I need the repository link to analyze the project. Please provide the `${repolink}`.

**tejasveesaini**: https://github.com/microsoft/playwright

**GitHub Copilot**: Ran Get file or directory contents 
Completed with input: {
  "path": "README.md",
  "repo": "playwright",
  "owner": "microsoft"
}

## 1. Repository Overview

**Purpose**
- Playwright is a framework for Web Testing and Automation. It solves the problem of cross-browser web automation by providing a single API to test Chromium, Firefox, and WebKit.
- Intended users are developers and QA engineers who need to perform end-to-end testing and automation of web applications across different browsers and platforms.

**Tech Stack**
- Languages: TypeScript, JavaScript, Python, .NET, Java (Playwright provides APIs for these languages)
- Frameworks/Libraries: Playwright Test (its own test runner)
- Tools & Services: Chromium, Firefox, WebKit (browsers for testing)

**Project Structure**
- The README.md file provides a high-level overview, installation instructions, capabilities, and examples.
- The project likely contains a `package.json` for Node.js dependencies, and potentially other language-specific package files (e.g., `requirements.txt` for Python, `pom.xml` for Java, `.csproj` for .NET) for its various language bindings.
- Test files are typically `.spec.ts` (for TypeScript/JavaScript).

**Key Features**
- Resilient and no flaky tests due to auto-wait and web-first assertions.
- Full isolation and fast execution using browser contexts.
- Powerful tooling including Codegen (test generation), Playwright Inspector (page inspection, selector generation), and Trace Viewer (post-mortem debugging).
- Supports testing scenarios across multiple tabs, origins, and users.
- Emulates mobile devices, geolocation, and permissions.
- Intercepts and routes network requests.

**Entry Points**
- `npm init playwright@latest` (for new projects or initializing Playwright Test)
- `npx playwright install` (to install supported browsers)
- Test files (e.g., `example.spec.ts`) are executed by the Playwright Test runner.

---

## 2. Prerequisites

- OS requirements: Linux, macOS, Windows are all supported. Specific system requirements can be found in the [Playwright documentation](https://playwright.dev/docs/intro#system-requirements).
- Required languages and versions: Node.js (for Playwright Test), Python, .NET, or Java depending on the language binding chosen.
- Required tools: npm (Node Package Manager) for installation.
- Environment variables: Not explicitly mentioned in the README.

---

## 3. Setup Instructions (Local)

1. **Initialize Playwright Test (recommended for new projects):**
   ```Shell
   npm init playwright@latest
   # Or to create a new project in a specific directory:
   npm init playwright@latest new-project
   ```
   This command will guide you through setting up a configuration file, example tests, and a GitHub Action workflow.

2. **Manual Installation (for existing projects):**
   a. Install Playwright Test as a development dependency:
      ```Shell
      npm i -D @playwright/test
      ```
   b. Install the supported browsers:
      ```Shell
      npx playwright install
      ```
      (Optionally, you can install specific browsers, refer to [install browsers](https://playwright.dev/docs/cli#install-browsers) for details.)

3. **Run Tests:**
   After installation, you can write your tests (e.g., in `example.spec.ts`) and run them using the Playwright Test runner. The exact command to run tests is not explicitly mentioned in the README, but typically it would be `npx playwright test` or a script defined in `package.json`.
