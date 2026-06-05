# Project: Lorraine AI MCP Server

## Status: In Progress
Last updated: 2026-06-02

---

## What this is

A Model Context Protocol server that exposes Lorraine AI v2's memory and planning files as tools for Claude. This makes Lorraine AI's context injectable into any Claude conversation without manual file-reading.

Built as part of the agent MVP. This is also the primary portfolio piece demonstrating MCP server design.

---

## Why this matters for the portfolio

- Demonstrates MCP server implementation (2026 market signal)
- Shows AI system design beyond tutorial level
- Produces a reusable pattern for personal AI systems
- Publishable as an open-source reference implementation

---

## Architecture

```
Lorraine AI MCP Server
├── tools/
│   ├── get_context()           → reads memory/context.md
│   ├── get_open_questions()    → reads memory/open_questions.md
│   ├── get_session_brief()     → generates brief from memory files
│   ├── get_weekly_plan()       → reads current week's plan
│   ├── log_win(win_data)       → appends to wins_log.md
│   └── log_decision(decision)  → appends to decisions_log.md
└── server.py                   → FastMCP server definition
```

- Model: claude-opus-4-20250514 (for decision sessions)
- Framework: FastMCP
- Tools: File I/O, markdown parsing
- Eval: Tool call accuracy, context injection correctness

---

## Progress

### Shipped
- [x] Basic FastMCP server running — 2026-05-28
- [x] `get_context()` tool working — 2026-05-29

### In progress
- [ ] `get_session_brief()` tool — target 2026-06-04
- [ ] `log_win()` and `log_decision()` write tools — target 2026-06-06

### Next
- [ ] `get_weekly_plan()` tool
- [ ] End-to-end test: boot sequence via MCP
- [ ] README and demo video
- [ ] Ship to GitHub

---

## Open technical questions

- How to handle concurrent writes to log files if multiple sessions run? (low risk for now — single user)
- Should get_session_brief() call Claude to summarise or just concatenate files? (start with concatenation, evaluate)

---

## Blockers

None currently.

---

## AI Engineer assessment

Score: 6/10
Note: Architecture is sound. Missing eval framework. Write tools need validation before shipping. README needed before calling this portfolio-ready.

---

## Eval plan

- [ ] Tool call accuracy: given known context.md content, does get_context() return correct data?
- [ ] Session brief quality: does get_session_brief() produce a useful brief vs manual reading?
- [ ] Write safety: does log_win() append correctly without corrupting the file?
- [ ] Minimum eval set: 10 test cases covering each tool
