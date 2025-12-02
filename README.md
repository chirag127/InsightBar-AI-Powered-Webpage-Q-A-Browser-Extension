# ContextualAI-Web-Content-Analyzer-Browser-Extension

![GitHub Logo Banner](https://img.shields.io/badge/Apex%20Architect%20Deployment-ContextualAI-Blue?style=for-the-badge&logo=github)

[![Build Status](https://img.shields.io/github/actions/workflow/status/chirag127/ContextualAI-Web-Content-Analyzer-Browser-Extension/ci.yml?label=Build&style=flat-square)](https://github.com/chirag127/ContextualAI-Web-Content-Analyzer-Browser-Extension/actions/workflows/ci.yml)
[![Code Coverage](https://img.shields.io/codecov/c/github/chirag127/ContextualAI-Web-Content-Analyzer-Browser-Extension?label=Coverage&style=flat-square)](https://codecov.io/gh/chirag127/ContextualAI-Web-Content-Analyzer-Browser-Extension)
[![Language](https://img.shields.io/github/languages/top/chirag127/ContextualAI-Web-Content-Analyzer-Browser-Extension?style=flat-square&color=yellow)](https://github.com/chirag127/ContextualAI-Web-Content-Analyzer-Browser-Extension)
[![License](https://img.shields.io/github/license/chirag127/ContextualAI-Web-Content-Analyzer-Browser-Extension?style=flat-square)](LICENSE)
[![GitHub Stars](https://img.shields.io/github/stars/chirag127/ContextualAI-Web-Content-Analyzer-Browser-Extension?style=flat-square)](https://github.com/chirag127/ContextualAI-Web-Content-Analyzer-Browser-Extension)

**⭐ Star this Repo** if you find this project valuable for enhancing information retrieval while browsing!

---

## BLUF: Value Proposition

**ContextualAI** transforms passive web browsing into an active, intelligent dialogue by leveraging the Gemini API to provide instant, context-aware Q&A directly on any webpage content. This extension enhances comprehension, speeds up research, and preserves critical information via integrated history saving and text-to-speech narration.

## Architecture Overview

This Browser Extension follows a highly decoupled, event-driven architecture utilizing modern web standards and strict separation between content scripts, background service workers, and the UI popup.

ascii
ContextualAI Browser Extension
------------------------------

+------------------+
|   User Interface |
|     (Popup/DOM)  |
+--------+---------+
         |
    (Messaging API)
         |
+--------v---------+
| Background Worker|
| (Service Worker) |
| - History Mgmt    |
| - API Key Proxy  |
+--------+---------+
         |
  (Content Scripts)
         |
+--------v---------+
| Active Web Page  |
| - DOM Capture    |
| - TTS Handler    |
+------------------+
         |
         v
+------------------+
|   External API   |
|   (Gemini Pro)   |
+------------------+


## Table of Contents

1. [BLUF: Value Proposition](#bluf-value-proposition)
2. [Architecture Overview](#architecture-overview)
3. [Features](#features)
4. [Tech Stack (2026 Standard)](#tech-stack-2026-standard)
5. [Development & Setup](#development--setup)
6. [Contributing Guidelines](#contributing-guidelines)
7. [Security & Compliance](#security--compliance)
8. [🤖 AI Agent Directives](#ai-agent-directives)

---

## Features

*   **AI-Powered Q&A:** Submit questions about visible page content to the Gemini API and receive synthesized answers instantly in the extension popup.
*   **Context Preservation:** Advanced text selection handling ensures queries are framed precisely based on user interaction.
*   **Text-to-Speech (TTS):** Convert Gemini responses into natural audio for hands-free consumption.
*   **Session History:** Securely saves all queries, context snippets, and answers locally within the browser's storage.
*   **Manifest V3 Compliance:** Built entirely on the latest security and performance standards for browser extensions.

## Tech Stack (2026 Standard)

| Component | Technology | Justification |
| :--- | :--- | :--- |
| Core Language | JavaScript (ESM) | Ubiquity and extension ecosystem standard. |
| Framework | **Vite** + Native Web Components | Maximum build speed and minimized runtime overhead for extensions. |
| State Mgmt | Signals API / Native Storage | Lightweight, performance-focused state handling. |
| API Interaction | Gemini API (via Proxy) | State-of-the-art reasoning capabilities. |
| Styling | Vanilla CSS Modules | Predictable scoping, zero framework bloat. |
| Linting/Formatting | **Biome** | Apex standard for unified, high-speed code quality enforcement. |

## Development & Setup

This project uses **JavaScript/TypeScript**, managed via **npm/yarn**, and configured for optimal development velocity using Vite.

1.  **Clone Repository:**
    bash
    git clone https://github.com/chirag127/ContextualAI-Web-Content-Analyzer-Browser-Extension.git
    cd ContextualAI-Web-Content-Analyzer-Browser-Extension
    
2.  **Install Dependencies (Apex uv/npm Standard):**
    bash
    npm install
    
3.  **Start Development Server (Hot Reload):**
    bash
    npm run dev
    
4.  **Build for Production:**
    bash
    npm run build
    

### Scripts Table

| Script | Command | Description |
| :--- | :--- | :--- |
| `dev` | `npm run dev` | Start development server with hot module reloading. |
| `build` | `npm run build` | Compile production-ready extension artifacts. |
| `lint` | `npx @biomejs/biome check .` | Run static analysis and linting checks. |
| `format` | `npx @biomejs/biome format --write .` | Automatically format all source files. |
| `test:unit` | `npx vitest` | Run unit tests. |
| `test:e2e` | `npx playwright test` | Execute End-to-End validation suites. |

### Guiding Principles

*   **SOLID:** Maintain single responsibility for Content Scripts, Background Workers, and UI components.
*   **DRY:** Abstract API interaction layers and storage handlers aggressively.
*   **YAGNI:** Do not implement features until explicitly required by the use case.

## Contributing Guidelines

Please refer to the comprehensive guidelines in [.github/CONTRIBUTING.md](./.github/CONTRIBUTING.md).

## Security & Compliance

Sensitive API keys are **NEVER** stored in client-side code. All external API calls (Gemini) MUST be proxied through the Background Service Worker to prevent key exposure, as detailed in [.github/SECURITY.md](./.github/SECURITY.md).

---

<details>
<summary>🤖 AI Agent Directives (Apex Architecture Protocol)</summary>

## 🤖 APEX AGENT DIRECTIVES: CONTEXTUALAI

**Project ID:** `ContextualAI-Web-Content-Analyzer-Browser-Extension`
**Objective:** Maintain a zero-defect, high-velocity development cycle for this modern Manifest V3 browser extension.

### 1. Architectural Mandate
*   **Pattern Adherence:** Strict adherence to the **Event-Driven Architecture (EDA)** model via Chrome Messaging API for inter-script communication.
*   **State Management:** Utilize native browser storage APIs (`chrome.storage.local`/`sync`) exclusively. Avoid third-party state libraries.
*   **Performance Pruning:** All bundle sizes must be aggressively tree-shaken using Vite build targets. Content scripts must load asynchronously and only when necessary.

### 2. Technology Stack Specification (LATE 2025)
*   **Language:** JavaScript/TypeScript (prefer TypeScript where interfaces are complex).
*   **Linter/Formatter:** **Biome** (enforced via pre-commit hook or CI).
*   **Unit Testing:** **Vitest** for isolated function/logic testing.
*   **E2E Testing:** **Playwright** for simulating user flows (e.g., opening popup, highlighting text, receiving AI response).
*   **API Key Management:** All Gemini API interactions must be routed through the `background.js` service worker to ensure the API key remains secret and never exposed to the content scripts or popup DOM.

### 3. Verification Commands
To ensure alignment with Apex standards, an agent must execute the following verification sequence:

1.  **Code Quality Check:** `npm run lint` (Must return zero errors).
2.  **Unit Test Pass:** `npm run test:unit` (Must achieve 90%+ coverage baseline).
3.  **Build Integrity Check:** `npm run build` (Must produce valid `manifest.json` structure for MV3).

**Action:** Any new feature implementation MUST include corresponding unit and integration tests.

</details>
