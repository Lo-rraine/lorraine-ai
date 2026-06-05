# Lorraine OS — MVP Definition

> The smallest version that creates meaningful value within 7 days.
> Everything marked [OPTIONAL] can wait. Do not build it yet.

---

## What the MVP Is

Three files. Two habits. One daily command.

That is it.

The full system is designed. The MVP is what you actually run.

---

## Required Files (7 total)

| File | Purpose | Can it wait? |
|---|---|---|
| `memory/context.md` | Your life state in one file | No — this is the foundation |
| `memory/open_questions.md` | Live list of unresolved decisions | No — this surfaces what needs attention |
| `memory/wins_log.md` | Running log of progress | No — this counters the amnesia problem |
| `plans/weekly/YYYY-Www.md` | This week's plan | No — without a plan, sessions drift |
| `system/BOOT.md` | Session startup protocol | No — this is the entry point |
| `system/DECISION.md` | Decision framework | No — this is where the system earns its value |
| `system/PLANNER.md` | Planning system | No — weekly planning is the highest-leverage habit |

**Everything else is [OPTIONAL] for the first 30 days.**

- `system/WELLBEING.md` — [OPTIONAL] Add in week 3
- `system/AI_ENGINEER.md` — [OPTIONAL] Add when you have a technical session
- `system/COMMUNICATION.md` — [OPTIONAL] Add when you need to draft something important
- `system/POSITIONING.md` — [OPTIONAL] Add during quarterly review
- `system/ORCHESTRATION.md` — [OPTIONAL] Reference only, not required for daily use
- `memory/patterns.md` — [OPTIONAL] Add after first monthly review
- `memory/relationships.md` — [OPTIONAL] Add when relevant
- `decisions/` folder — [OPTIONAL] Add when first decision is made

---

## Required Workflows (2 total)

### Workflow 1 — Morning Startup (10 minutes)

```
1. Open context.md — read it. Update any stale facts.
2. Open open_questions.md — read the list. Is there anything urgent?
3. Open this week's plan — what are today's rocks?
4. Paste into Claude Code:
   "Read memory/context.md and plans/weekly/[this week].md.
    Give me a 5-line session brief and confirm today's rocks."
5. Start working.
```

### Workflow 2 — Weekly Planning (30 minutes, Sunday)

```
1. Open last week's plan. Mark rocks complete or incomplete.
2. Paste into Claude Code:
   "Read memory/context.md and memory/open_questions.md.
    Run a weekly planning session. Set theme, 3 rocks, learning block."
3. Save the output to plans/weekly/YYYY-Www.md.
4. Git commit.
```

**Everything else — daily reflection, monthly review, decision sessions — runs when needed. Not on a schedule for the first 7 days.**

---

## Required Commands

### Git setup (Day 1 only)

```bash
cd lorraine-ai-v2
git init
git add -A
git commit -m "init: Lorraine OS v1 — day 1"
```

### Session commit (end of every session)

```bash
git add -A
git commit -m "session: YYYY-MM-DD — [one sentence]"
```

### Start a Claude Code session

```bash
# In Claude Code, paste:
"Read system/BOOT.md and memory/context.md. Run boot sequence."
```

### Run a decision

```bash
# In Claude Code, paste:
"Read system/DECISION.md and memory/context.md.
 I need to decide: [one sentence decision]. Run the decision protocol."
```

---

## Required Habits (2 total)

**Habit 1 — Open Lorraine OS before starting work.**
Not after. Not during. Before.
Time: 10 minutes.
Payoff: You start with a plan instead of reacting.

**Habit 2 — Sunday planning session.**
30 minutes. Non-negotiable.
Payoff: You go into Monday with intention instead of anxiety.

Everything else is built on these two habits.

---

## Explicitly Out of Scope for Week 1

- [ ] Building the MCP server
- [ ] Automating anything
- [ ] The full orchestration layer
- [ ] Wellbeing scoring system
- [ ] Monthly or quarterly reviews
- [ ] Relationships file
- [ ] Patterns file
- [ ] Any advisor beyond DECISION.md and PLANNER.md

**Do not build these yet. Use the system first. Build what you actually need.**
