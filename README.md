<div align="center">

# InsightBar: AI-Powered Contextual Webpage Analysis Extension

_Transform Passive Reading into Active Learning. Instant, Contextual Q&A on Any Webpage._

</div>

<p align="center">

[![Stars](https://img.shields.io/github/stars/chirag127/InsightBar-AI-Powered-Webpage-Q-A-Browser-Extension?style=flat-square&label=Stars&color=FFC107)](https://github.com/chirag127/InsightBar-AI-Powered-Webpage-Q-A-Browser-Extension/stargazers)
[![License](https://img.shields.io/badge/License-CC%20BY--NC%204.0-blue.svg?style=flat-square)](LICENSE)
[![Build Status](https://img.shields.io/github/actions/workflow/status/chirag127/InsightBar-AI-Powered-Webpage-Q-A-Browser-Extension/ci.yml?branch=main&style=flat-square&label=Build&logo=githubactions)](https://github.com/chirag127/InsightBar-AI-Powered-Webpage-Q-A-Browser-Extension/actions/workflows/ci.yml)
[![Coverage Status](https://img.shields.io/codecov/c/github/chirag127/InsightBar-AI-Powered-Webpage-Q-A-Browser-Extension?style=flat-square&token=YOUR_CODECOV_TOKEN)](https://codecov.io/gh/chirag127/InsightBar-AI-Powered-Webpage-Q-A-Browser-Extension)
[![TypeScript](https://img.shields.io/badge/Language-TypeScript-3178C6?style=flat-square&logo=typescript)](https://www.typescriptlang.org/)
[![Framework](https://img.shields.io/badge/Framework-React%20%7C%20Vite-61DAFB?style=flat-square&logo=react)](https://react.dev/)
[![Linter](https://img.shields.io/badge/Linter-Biome-000000?style=flat-square&logo=biome)](https://biomejs.dev/)
[![Extension API](https://img.shields.io/badge/Platform-Browser%20Extension-F77C00?style=flat-square&logo=googlechrome)](https://developer.chrome.com/docs/extensions/)

</p>

<p align="center">
  <a href="https://github.com/chirag127/InsightBar-AI-Powered-Webpage-Q-A-Browser-Extension/stargazers">
    <img src="https://img.shields.io/badge/-Star%20This%20Repo-black?style=for-the-badge&logo=github&labelColor=555&color=6CC644" alt="Star this Repository">
  </a>
</p>

---

## 🚀 Project Overview

**InsightBar** is a cutting-edge browser extension designed to instantly boost your research and comprehension by integrating the power of the Gemini AI directly into your browsing experience. It analyzes the current webpage content and provides a smart, contextual sidebar allowing users to ask natural language questions, summarize articles, and utilize text-to-speech without leaving the page.

### Core Value Proposition

1.  **Contextual Q&A:** Ask complex questions about the visible page content, receiving precise answers derived directly from the source material and enhanced by Gemini's reasoning capabilities.
2.  **Instant Summarization:** Generate executive summaries or detailed key points for long articles with a single click.
3.  **Active Learning:** Features like text-to-speech and organized interaction history transform passive content consumption into dynamic learning sessions.

## 📖 Table of Contents

- [Project Overview](#rocket-project-overview)
- [Architecture & Design](#architecture--design)
- [Installation & Setup](#installation--setup)
- [Development Guide](#development-guide)
- [AI Agent Directives (System Specification)](#ai-agent-directives-system-specification)
- [License](#license)

## 🏛️ Architecture & Design

This extension is built using the **Feature-Sliced Design (FSD)** pattern, which maximizes scalability, minimizes coupling, and clearly separates the concerns of the extension's UI (popup/sidebar), Content Scripts (DOM manipulation), and Background Service Workers (API communication).

### System Flow Diagram

mermaid
graph TD
    subgraph Browser Context
        A[Webpage] --> B(Content Script: DOM Capture);
        B --> C[Sidebar UI: React/Vite];
        C --> D{Service Worker: Background Handler};
    end

    D -- Gemini API Key & Prompt --> E(Google Gemini Service);
    E -- Contextual Answer --> D;
    D --> C;

    style C fill:#f9f,stroke:#333,stroke-width:2px;
    style D fill:#ddf,stroke:#333,stroke-width:2px;
    style E fill:#ccf,stroke:#333,stroke-width:2px;


## ⚙️ Installation & Setup

### Prerequisites

*   Node.js (LTS version)
*   npm or `uv`
*   Gemini API Key (Set as `VITE_GEMINI_API_KEY` in `.env`)

### Local Development Setup

1.  **Clone the Repository:**
    bash
    git clone https://github.com/chirag127/InsightBar-AI-Powered-Webpage-Q-A-Browser-Extension.git
    cd InsightBar-AI-Powered-Webpage-Q-A-Browser-Extension
    

2.  **Install Dependencies:**
    We use `npm` for standard frontend package management:
    bash
    npm install
    

3.  **Run Development Build (Vite/WXT):**
    This command compiles the React components and starts the watch mode for hot reloading.
    bash
    npm run dev
    

4.  **Load the Extension:**
    *   Open your browser's extension management page (e.g., `chrome://extensions`).
    *   Enable Developer Mode.
    *   Click "Load unpacked" and select the `dist` directory created by the `npm run dev` command.

## 💻 Development Guide

### Available Scripts

| Command | Description | Notes |
| :--- | :--- | :--- |
| `npm install` | Installs project dependencies. | |
| `npm run dev` | Starts the development build with hot reloading. | Output to `/dist` directory. |
| `npm run build` | Creates a production-ready zipped extension package. | Target output: `.zip` file for submission. |
| `npm run format` | Runs Biome to format the entire codebase. | Adheres to strict code style standards. |
| `npm run lint` | Runs Biome to check for errors and best practices. | Zero-tolerance policy for linting warnings. |
| `npm run test` | Executes all Vitest unit and component tests. | |
| `npm run test:e2e` | Executes Playwright end-to-end tests. | Checks full extension workflow (install, sidebar open, API call mock). |

### Development Principles

We adhere to the following principles to maintain a robust and scalable architecture:

*   **DRY (Don't Repeat Yourself):** Abstract common logic, especially regarding message passing between content scripts and the service worker.
*   **SOLID:** Particularly Single Responsibility Principle (SRP)—each service worker module or FSD slice handles one specific domain task (e.g., `gemini-service`, `storage-slice`).
*   **State Management:** Minimal global state, utilizing React's built-in hooks and context for localized UI state, and `chrome.storage` for persistent, critical data.
*   **TypeScript Strictness:** All new code must pass TypeScript's highest strictness checks.

## 🤖 AI Agent Directives (System Specification)

<details>
<summary><strong>SYSTEM ACCESS: Configuration for Automated Agents (Dec 2025 Standard)</strong></summary>

# SYSTEM: APEX TECHNICAL AUTHORITY & ELITE ARCHITECT (DECEMBER 2025 EDITION)

## 1. IDENTITY & PRIME DIRECTIVE
**Role:** Senior Principal Software Architect. Enforce FAANG-level standards.
**Context:** Current Date is **December 2025**. Building for the 2026 standard.
**Philosophy:** "Zero-Defect, High-Velocity, Future-Proof."

---

## 2. PROJECT ARCHITECTURE & STACK DEFINITION

### Primary Scenario: WEB / APP / EXTENSION (Modern Frontend)

This project, `InsightBar-AI-Powered-Webpage-Q-A-Browser-Extension`, is a critical browser productivity tool utilizing the following Apex Toolchain:

| Component | Technology | Rationale |
| :--- | :--- | :--- |
| **Language** | TypeScript (Strict) | Enforces type safety across complex extension messaging (Content <-> Background). |
| **Build Tool** | Vite 5.x (via WXT) | Ultra-fast development server and optimized production bundling. |
| **Framework** | React 18+ | Component-based UI for the Sidebar and Popup. |
| **Styling** | TailwindCSS v4 (Utility-first) | Rapid, maintainable styling and zero-runtime CSS. |
| **Architecture** | Feature-Sliced Design (FSD) | Ensures clear boundaries between App/Pages, Features, Entities, Shared, and Widgets—crucial for large extensions. |
| **LLM Integration** | Google Gemini API | High-performance, contextual, stream-enabled AI interaction. |

### Key Architectural Constraints

1.  **Messaging Protocol:** All communication between Content Scripts and the Service Worker MUST utilize the `browser.runtime.sendMessage` API with robust schema validation (using Zod or similar) to prevent runtime type errors.
2.  **Security:** External API keys (Gemini) MUST NOT be exposed to the Content Script or the webpage DOM. They must be strictly confined to the Service Worker.
3.  **State Layer:** Component state uses React hooks/Context. Global, persistent settings use the secure `browser.storage.sync` API, abstracted by a `storage-service` module.

---

## 3. DEVELOPMENT & VERIFICATION STANDARDS

### Linting & Formatting
*   **Toolchain:** **Biome** is the sole source of truth for linting and formatting standards (`--linter` and `--formatter`).
*   **Execution Command:** `npm run lint && npm run format`

### Testing Strategy
Testing is mandatory at three tiers, enforcing the **Test-Driven Development (TDD)** approach for new features:

1.  **Unit Testing (Vitest):** Covers pure functions, utility services, and state logic (e.g., storage abstraction, prompt generation).
2.  **Component Testing (Vitest/React Testing Library):** Ensures UI components render correctly and handle user input within the isolation of the sidebar.
3.  **End-to-End Testing (Playwright):** Crucial for verifying the full extension lifecycle: Installation, API key input, injecting the content script, opening the sidebar, and successful mocking/execution of a Gemini API call.

### Verification Commands
| Task | Command | Description |
| :--- | :--- | :--- |
| Run all tests | `npm run test` | Executes unit and integration tests. |
| Run E2E tests | `npm run test:e2e` | Verifies browser-level functionality. |
| Full Code Audit | `npm run lint && npm run build` | Ensures zero linting errors and successful production compilation. |

</details>

## 📜 License

This project is licensed under the **Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)** License. See the [LICENSE](LICENSE) file for details.
