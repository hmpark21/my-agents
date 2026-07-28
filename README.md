# My Agents

Custom Claude Code agent definitions from my personal agent workspace.

## Install

```bash
cp agents/*.md ~/.claude/agents/
```

`CLAUDE.md` is the root orchestration prompt (Brain agent) — copy it separately to your project root or `~/.claude/` if needed.

## Agents

### Orchestration & Memory

- **CLAUDE.md (Brain)** — Root orchestration prompt. Acts as chief-of-staff: interprets requests, routes work to staff agents by domain (sales, marketing, engineering, data, finance, legal, HR, and more), reviews results, and reports back with a single consolidated summary. Includes memory policy, safety rules, and routing logic.
- **memory-agent** — Automatically captures session context into `.auto-memory/` and `CLAUDE.md`. Analyzes session summaries and git traces to record project context, user preferences, and work patterns, keeping them retrievable across sessions.

### Content & Deliverables

- **design-system** — Unified design-system agent. Generates PPT decks (.pptx), websites (HTML), and promo cards with consistent design tokens: Pretendard-only typography, custom logo support, fixed layout grids, and dense content placement.
- **docx-builder** — Word document (.docx) specialist. Writes Korean business documents with python-docx: Malgun Gothic, 10–11pt body, A4 layout, bullet-oriented structure, mandatory source citations, outline confirmation before writing, and automatic self-review after. Accepts handoff packages from the researcher agent.
- **web-builder** — Website build specialist. Confirms a site plan (purpose, structure, stack), builds it, then runs automatic screenshot capture and self-review (mechanical checks + visual inspection). Supports single landing pages, multi-page static sites, and React/Next.js apps, choosing the stack to match complexity.
- **translator** — Professional translation agent focused on accurate, natural, reader-friendly translations that preserve the source meaning.

### Research & Reporting

- **researcher** — Research specialist. Confirms a research outline first, then explores web, documents, and internal sources in parallel to produce an evidence-based report. Every fact, figure, and quote is cited; final output is a Word (.docx) report with automatic pre-build self-review for gaps, sources, and consistency.
- **news-reporter** — Collects and organizes the last 26 hours of economy/IT news every morning at 8:00 KST, then saves a markdown + PDF report without user confirmation. (Scheduling handled by launchd.)
- **stock-reporter** — Analyzes the 5 hottest themes and top 5 companies per theme for KOSPI (8:00 KST) and NASDAQ (21:30 KST) daily, saving markdown reports without user confirmation. (Scheduling handled by launchd.)

### Code Review

- **code-reviewer** — Expert code review specialist. Proactively reviews code for quality, security, and maintainability. Use immediately after writing or modifying code.
- **java-reviewer** — Expert Java and Spring Boot reviewer specializing in layered architecture, JPA patterns, security, and concurrency.
- **python-reviewer** — Expert Python reviewer specializing in PEP 8 compliance, Pythonic idioms, type hints, security, and performance.
- **typescript-reviewer** — Expert TypeScript/JavaScript reviewer specializing in type safety, async correctness, Node/web security, and idiomatic patterns.

### Build & Planning

- **planner** — Expert planning specialist for complex features and refactoring. Breaks work into phases, identifies dependencies and risks.
- **java-build-resolver** — Java/Maven/Gradle build and dependency error resolution specialist. Fixes build errors with minimal changes.
- **pytorch-build-resolver** — PyTorch runtime, CUDA, and training error resolution specialist. Fixes tensor shape mismatches, device errors, gradient issues, DataLoader problems, and mixed-precision failures.
- **doc-updater** — Documentation and codemap specialist. Updates codemaps, generates `docs/CODEMAPS/*`, and keeps READMEs and guides current.
