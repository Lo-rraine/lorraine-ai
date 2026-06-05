# BOOT.md — Session Startup Protocol

> Run this at the start of every Claude Code session. It loads context, detects intent, and activates the right advisors.

---

## Boot Sequence

When a new session starts, Claude Code reads this file and executes the following:

### Step 1 — Load Memory

```
Read: memory/context.md
Read: memory/open_questions.md
Read: memory/decisions_log.md (last 5 entries)
Read: memory/wins_log.md (last 3 entries)
```

Produce a **Session Brief** in this format:

```
## Session Brief — [DATE]

**Last session:** [date] — [one sentence summary]
**Open decisions:** [list from open_questions.md]
**Current priorities:** [top 3 from context.md]
**Wins since last session:** [from wins_log.md]
**Watch items:** [anything flagged in context.md]
**Wellbeing flag:** [last check-in status from wellbeing/checkins.md]
```

---

### Step 2 — Detect Intent

After the Session Brief, ask:

> "What are we working on today? Or shall I run the standard morning startup?"

Classify the session into one of these modes:

| Mode | Trigger | Advisors Activated |
|---|---|---|
| `morning-startup` | "morning", "start my day", no specific topic | Memory + Planner + Wellbeing |
| `decision` | "should I", "deciding", "choice between" | Memory + Decision + relevant advisors |
| `technical-work` | code, architecture, AI project | Memory + AI Engineer |
| `career-move` | job, opportunity, interview, offer | Memory + Positioning |
| `communication` | draft, message, email, talk, pitch | Memory + Communication |
| `planning` | weekly review, plan, priorities | Memory + Planner |
| `wellbeing-check` | feeling, energy, stressed, burned out | Memory + Wellbeing |
| `open` | anything else | Memory + relevant advisors on demand |

---

### Step 3 — Confirm and Proceed

State the detected mode and ask for confirmation if unclear:

> "Looks like a [mode] session. Activating [advisors]. Ready when you are."

---

## Boot Command Reference

Copy and paste any of these to start a session:

```
# Standard morning startup
"Boot Lorraine AI. Run morning startup."

# Decision session
"Boot Lorraine AI. I need to make a decision about [topic]."

# Deep work session
"Boot Lorraine AI. Working on [project name] today."

# Weekly review
"Boot Lorraine AI. Run the weekly review."

# Wellbeing check
"Boot Lorraine AI. Check in on how I'm doing."
```

---

## What Claude Code Does on Boot

```python
# Pseudocode — Claude Code execution
1. read("memory/context.md")
2. read("memory/open_questions.md")
3. read("memory/decisions_log.md")[-5:]
4. read("memory/wins_log.md")[-3:]
5. read("wellbeing/checkins.md")[-1:]
6. generate_session_brief()
7. detect_intent(user_input)
8. activate_advisors(intent_mode)
9. proceed()
```

---

## Session Close Protocol

At the end of every session, Claude Code:

1. **Updates** `memory/context.md` with any changed facts
2. **Appends** to `logs/YYYY-MM-DD-session.md`
3. **Appends** to `memory/decisions_log.md` if a decision was made
4. **Appends** to `memory/wins_log.md` if a win was logged
5. **Updates** `memory/open_questions.md` (remove resolved, add new)
6. **Prompts**: "Session complete. Shall I commit these changes to Git?"

Git commit message format:
```
session: YYYY-MM-DD — [one sentence summary of session]
```
