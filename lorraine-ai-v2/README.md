# Lorraine AI v2 — Personal Operating System

> A personal AI operating system built in Claude Code. Markdown is the source of truth. Git is the version history. You are the CEO.

---

## Quick Start

```bash
# Start a session
cat system/BOOT.md

# Morning startup
cat system/WORKFLOWS.md#morning

# Run a decision
cat system/DECISION.md

# Weekly review
cat system/PLANNER.md
```

---

## Architecture Overview

```
lorraine-ai-v2/
├── README.md                    ← You are here
├── system/                      ← Core skill files (the advisors)
│   ├── BOOT.md                  ← Session startup protocol
│   ├── MEMORY.md                ← Memory Lorraine
│   ├── PLANNER.md               ← Planner Lorraine
│   ├── DECISION.md              ← Decision Lorraine
│   ├── WELLBEING.md             ← Wellbeing Lorraine
│   ├── AI_ENGINEER.md           ← AI Engineer Lorraine
│   ├── COMMUNICATION.md         ← Communication Lorraine
│   ├── POSITIONING.md           ← Market Positioning Lorraine
│   ├── ORCHESTRATION.md         ← Orchestration rules
│   └── WORKFLOWS.md             ← Daily / weekly / monthly workflows
├── memory/
│   ├── context.md               ← Current life context (updated each session)
│   ├── decisions_log.md         ← Running log of all decisions made
│   ├── wins_log.md              ← Running log of wins and progress
│   ├── open_questions.md        ← Questions Lorraine is sitting with
│   ├── relationships.md         ← Key people and relationship notes
│   └── patterns.md              ← Observed patterns and recurring themes
├── plans/
│   ├── daily/                   ← YYYY-MM-DD.md
│   ├── weekly/                  ← YYYY-Www.md
│   ├── monthly/                 ← YYYY-MM.md
│   ├── quarterly/               ← YYYY-Qn.md
│   └── annual/                  ← YYYY.md
├── decisions/                   ← YYYY-MM-DD-slug.md (one file per decision)
├── projects/                    ← One folder per active project
├── wellbeing/
│   ├── checkins.md              ← Running wellbeing check-in log
│   └── patterns.md              ← Observed wellbeing patterns
├── reviews/                     ← Periodic review outputs
├── logs/                        ← Session logs (YYYY-MM-DD-session.md)
└── skills/                      ← v1 advisor files (reference)
```

---

## Component Map

| Component | File | Always On? | Trigger |
|---|---|---|---|
| Memory | system/MEMORY.md | ✅ Yes | Every session |
| Orchestration | system/ORCHESTRATION.md | ✅ Yes | Every session |
| Planner | system/PLANNER.md | ✅ Yes | Every session |
| Wellbeing | system/WELLBEING.md | ✅ Yes | Every session |
| Decision | system/DECISION.md | Conditional | Decision needed |
| AI Engineer | system/AI_ENGINEER.md | Conditional | Technical work |
| Communication | system/COMMUNICATION.md | Conditional | Comms needed |
| Positioning | system/POSITIONING.md | Conditional | Career / market question |

---

## Design Principles

1. **Markdown is the database.** Every piece of state lives in a `.md` file.
2. **Git is the version history.** Every update is a commit.
3. **Memory before advice.** Context is loaded before any advisor speaks.
4. **One recommendation.** Decision Lorraine resolves conflicts. No endless council debate.
5. **Simplicity over elegance.** If it can't be maintained in 30 minutes per week, it won't be used.
6. **Lorraine is the CEO.** The system advises. Lorraine decides.

---

## Session Protocol

Every session follows this sequence:

```
1. BOOT      → load memory/context.md
2. INTENT    → detect what this session is about
3. PLAN      → surface today's plan and open items
4. WELLBEING → quick state check
5. WORK      → activate relevant conditional advisors
6. CLOSE     → update memory, log session, commit
```
