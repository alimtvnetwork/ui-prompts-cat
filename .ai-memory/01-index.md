# Repository Context & AI Architecture Index

> **Repository:** `ui-prompts-cat`
> **Target:** `.ai-memory/01-index.md`
> **Purpose:** Master repository index, directory router, and operational architecture guide for AI agents.

---

## 1. Repository Architecture Overview

`ui-prompts-cat` is a React, TypeScript, and Tailwind CSS UI prompts catalog application:
- **Frontend Stack (`src/`):** React 19, TypeScript, Vite, Tailwind CSS, Lucide React, Radix UI.
- **Prompt Catalog (`prompts/`):** Categorized markdown prompts and system instructions.
- **Canonical Prompts (`01-prompts/`):** Execution workflows, reading protocols, and coding standards.
- **AI Agent Capabilities (`.agents/skills/`):** Antigravity agent skills.
- **AI Memory (`.ai-memory/`):** Institutional memory, active plans, issue logs.

---

## 2. Directory Navigation Router

| Location | Purpose | Key Entrypoint |
|---|---|---|
| `prompts/` | UI prompt catalog files | `prompts/` |
| `01-prompts/` | Canonical execution prompts & workflows | `01-prompts/03-read-write/` |
| `.agents/skills/` | Installed Antigravity agent skills | `.agents/skills/` |
| `.ai-memory/what-to-read.md` | Authoritative reading order for agents | `.ai-memory/what-to-read.md` |
| `.ai-memory/strictly-avoid.md` | Hard prohibitions & CODE RED constraints | `.ai-memory/strictly-avoid.md` |
| `src/` | React UI components, views, and state | `src/` |
