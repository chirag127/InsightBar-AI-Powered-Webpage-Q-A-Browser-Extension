# 🤝 Contributing to InsightBar-AI-Powered-Webpage-Q-A-Browser-Extension

As the Apex Technical Authority, we adhere to the **Zero-Defect, High-Velocity, Future-Proof** philosophy. Contributions that uphold these standards are highly valued.

This repository is built on a modern **TypeScript/React/Vite** stack, utilizing strict typing and functional design principles.

## 1. Prerequisites: The Apex Toolkit

Before contributing, ensure your local environment is configured to meet our strict tooling requirements. We enforce quality via speed and automation.

1.  **Node.js:** Version 20 LTS or higher.
2.  **Git:** Must support modern features (e.g., rebase workflows).
3.  **Biome:** Installed and configured for formatting and linting checks locally.

bash
# Ensure Biome is available globally or managed via project scripts
npm install -g @biomejs/cli


## 2. Workflow: Feature-Sliced & Verified Development

We mandate a high-fidelity development cycle based on **Feature-Sliced Design (FSD)** for clean architectural boundaries.

### A. Branching Strategy

All development must occur on feature branches originating from `main`. We use a **Rebase and Squash** workflow before merging.

1.  **Create Branch:**
    bash
    git checkout main
    git pull origin main
    git checkout -b feat/descriptive-feature-name
    

2.  **Commit Early, Rebase Often:** Keep commits atomic and clean. Use `git rebase -i` to squash related fixups into coherent logical units before opening a Pull Request.

### B. Code Quality Gates

Every contribution *must* pass local quality checks before pushing. **Never rely solely on CI.**

1.  **Linting & Formatting Check:** Verify code style compliance.
    bash
    npm run lint
    

2.  **Unit Testing:** Ensure all new functionality is covered by tests using **Vitest**.
    bash
    npm run test:unit
    

3.  **End-to-End (E2E) Validation:** Run Playwright scenarios to validate critical user flows.
    bash
    npm run test:e2e
    

## 3. Pull Request (PR) Submission Protocol

Your PR must serve as a complete architectural summary of the change.

1.  **Self-Review First:** Use the provided PR Template (`.github/PULL_REQUEST_TEMPLATE.md`). Address all points before requesting review.
2.  **Reference Issues:** Link to any corresponding GitHub Issues using standard keywords (e.g., `Fixes #123`).
3.  **Target Branch:** Ensure your branch targets `main`.
4.  **Minimalist Approvals:** PRs must pass all automated CI checks (Build, Test, Lint) before a human reviewer will engage. Expect automated checks to fail if local quality gates were ignored.

## 4. Architectural Adherence

Contributions must align with the stated architectural principles documented in `AGENTS.md`:

*   **SOLID Principles:** Mandatory adherence, especially Single Responsibility and Dependency Inversion.
*   **DRY (Don't Repeat Yourself):** Aggressively refactor duplication.
*   **YAGNI (You Aren't Gonna Need It):** Avoid premature optimization or speculative features.

## 5. Reporting Issues

If you encounter a bug or have a feature request, please use the defined templates located in `.github/ISSUE_TEMPLATE/bug_report.md` to provide maximum diagnostic information immediately.

--- 
*By contributing to this repository, you agree that your contributions will be licensed under the **CC BY-NC 4.0** license.*