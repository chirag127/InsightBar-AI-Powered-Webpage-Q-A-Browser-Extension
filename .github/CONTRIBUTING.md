# Contributing to ContextualAI

First and foremost, thank you for considering contributing to `ContextualAI-Web-Content-Analyzer-Browser-Extension`. Your involvement is essential for making this tool more powerful and intelligent. This document provides a complete guide to our contribution process and standards.

We operate under a strict **Code of Conduct**. By participating, you are expected to uphold this code. Please report any unacceptable behavior.

## Table of Contents
- [How Can I Contribute?](#how-can-i-contribute)
  - [Reporting Bugs](#reporting-bugs)
  - [Suggesting Enhancements](#suggesting-enhancements)
  - [Submitting Pull Requests](#submitting-pull-requests)
- [Development Environment Setup](#development-environment-setup)
- [Pull Request Process](#pull-request-process)
- [Architectural & Coding Standards](#architectural--coding-standards)
- [Commit Message Guidelines](#commit-message-guidelines)

## How Can I Contribute?

### Reporting Bugs
This project uses GitHub Issues for bug tracking. Before submitting a bug report, please perform a comprehensive search of the existing [issues](https://github.com/chirag127/ContextualAI-Web-Content-Analyzer-Browser-Extension/issues) to ensure the problem has not already been reported.

If you identify a new bug, provide a detailed, high-quality report by opening a new issue using our official [Bug Report Template](https://github.com/chirag127/ContextualAI-Web-Content-Analyzer-Browser-Extension/issues/new?template=bug_report.md). Precision in bug reporting is the first step to a rapid resolution.

### Suggesting Enhancements
We welcome strategic suggestions for new features or improvements to existing functionality. To propose an enhancement, please open an issue and provide a detailed specification. Explain the core use case, the problem it solves, and why the enhancement would be a valuable addition to the ecosystem.

### Submitting Pull Requests
For bug fixes or new features, please adhere to the [Pull Request Process](#pull-request-process) detailed below to ensure a smooth and efficient review cycle.

## Development Environment Setup

To configure the extension on your local machine for development and testing, follow these steps with precision.

1.  **Prerequisites:**
    *   [Node.js](https://nodejs.org/) (LTS version)
    *   [npm](https://www.npmjs.com/) (comes with Node.js)

2.  **Fork & Clone the Repository:**
    bash
    git clone https://github.com/YOUR_USERNAME/ContextualAI-Web-Content-Analyzer-Browser-Extension.git
    cd ContextualAI-Web-Content-Analyzer-Browser-Extension
    

3.  **Install Dependencies:**
    bash
    npm install
    

4.  **Build the Extension:**
    This project uses a modern build tool (e.g., Vite) to bundle assets and ensure optimal performance.
    bash
    # Run the development build with hot-reloading
    npm run dev

    # Create a production-ready, optimized build in the `dist/` directory
    npm run build
    

5.  **Load the Unpacked Extension in Your Browser:**

    *   **Google Chrome / Brave:**
        1.  Navigate to `chrome://extensions`.
        2.  Enable "Developer mode" in the top-right corner.
        3.  Click "Load unpacked".
        4.  Select the generated `dist` directory from the project folder.

    *   **Mozilla Firefox:**
        1.  Navigate to `about:debugging#/runtime/this-firefox`.
        2.  Click "Load Temporary Add-on...".
        3.  Select the `manifest.json` file inside the `dist` directory.

## Pull Request Process

1.  **Branching Strategy:** Create a new branch from `main`. Use a descriptive, kebab-case naming convention.
    bash
    # For new features
    git checkout -b feature/your-amazing-feature

    # For bug fixes
    git checkout -b fix/issue-short-description
    
2.  **Implementation:** Write clean, efficient, and well-documented code that adheres to the established [Architectural & Coding Standards](#architectural--coding-standards).

3.  **Lint & Format:** Ensure your code passes all quality gates by running the linter and formatter.
    bash
    npm run lint
    

4.  **Commit Changes:** Adhere strictly to our [Commit Message Guidelines](#commit-message-guidelines).
    bash
    git commit -m "feat(core): implement AI-powered summarization engine"
    

5.  **Push to Your Fork:**
    bash
    git push origin feature/your-amazing-feature
    

6.  **Open a Pull Request:** Navigate to the [main repository's pull requests](https://github.com/chirag127/ContextualAI-Web-Content-Analyzer-Browser-Extension/pulls) and open a new PR from your forked branch. Provide a detailed description and link any relevant issues (e.g., "Closes #123").

## Architectural & Coding Standards

*   **Technology Stack:** The extension is built with modern JavaScript (ES6+), HTML5, and CSS3. We leverage standard WebExtension APIs to ensure cross-browser compatibility and maintainability.
*   **Architecture:** We enforce a clean, modular architecture with a clear separation of concerns:
    *   `background.js`: The central service worker for handling background tasks, state management, and external API communication.
    *   `content-scripts/`: Isolated scripts that interact directly with web page DOMs.
    *   `popup/` or `ui/`: Contains the UI components and logic for the extension's user-facing interface.
*   **Code Style:** We use a strict linter and formatter (e.g., Biome or ESLint/Prettier) to maintain a consistent, high-quality codebase. All contributions must pass the `npm run lint` check without errors.
*   **Core Principles:** Adhere to software engineering principles like DRY (Don't Repeat Yourself) and SOLID where applicable. Code must be self-documenting, with complex logic supplemented by clear JSDoc comments.

## Commit Message Guidelines

We enforce the [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) specification. This creates an explicit commit history that is easy to navigate and automate.

The format is: `<type>(<scope>): <subject>`

*   **`feat`**: A new feature for the user.
*   **`fix`**: A bug fix for the user.
*   **`docs`**: Documentation-only changes.
*   **`style`**: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc).
*   **`refactor`**: A code change that neither fixes a bug nor adds a feature.
*   **`perf`**: A code change that improves performance.
*   **`test`**: Adding missing tests or correcting existing tests.
*   **`chore`**: Changes to the build process or auxiliary tools and libraries.