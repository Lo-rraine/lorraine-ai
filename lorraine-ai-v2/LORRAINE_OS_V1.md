# Lorraine OS v1 — The Version You Actually Run

> "If I were Lorraine, this is the version I would use every day."

This is not the full system. This is the real system — the smallest set of files, commands, and habits that creates compounding value with the least possible friction.

---

## The Files

Six files. That is it.

```
lorraine-ai-v2/
├── memory/
│   ├── context.md          ← Your life state. Keep this accurate.
│   ├── open_questions.md   ← Every decision you're sitting with.
│   └── wins_log.md         ← Evidence you are making progress.
├── plans/
│   └── weekly/
│       └── YYYY-Www.md     ← This week's plan. One file.
└── system/
    ├── DECISION.md         ← How to make decisions.
    └── PLANNER.md          ← How to plan.
```

Everything else (WELLBEING.md, AI_ENGINEER.md, COMMUNICATION.md, POSITIONING.md) is available when you need it. You do not open it unless a session calls for it.

---

## The Daily Command

Every morning, paste this into Claude Code:

```
Read memory/context.md and memory/open_questions.md.

Session brief: tell me my open decisions, current priorities, and any watch items.
Then tell me: what are the 3 most important things for me to do today?
```

Adjust the 3 things. Start.

That is the morning startup. 8 minutes.

---

## The Weekly Command

Every Sunday, paste this into Claude Code:

```
Read system/PLANNER.md, memory/context.md, and memory/open_questions.md.

Weekly planning session:
1. What is this week's theme?
2. What are 3 rocks (non-negotiables)?
3. What is the learning block goal and project?
4. What am I explicitly NOT doing this week?
5. What decision needs to be made before Friday?

Output a complete weekly plan I can save.
```

Save the output to `plans/weekly/YYYY-Www.md`. 30 minutes.

---

## The Decision Command

When you need to decide something, paste this:

```
Read system/DECISION.md and memory/context.md.

Decision session: [state the decision in one sentence]

Run the full protocol. Frame it, surface advisor positions, map conflicts,
apply the hierarchy, run the tests, make one unambiguous recommendation.
Tell me the first action and the review trigger.
```

Read it. Make the call. Save to `decisions/YYYY-MM-DD-slug.md`. 30 minutes.

---

## The Time Commitment

| Activity | Time | Frequency |
|---|---|---|
| Morning startup | 8 minutes | Every workday |
| Session close (update + commit) | 5 minutes | Every workday |
| Weekly planning | 30 minutes | Every Sunday |
| Decision session | 30 minutes | When needed |
| Context update | 5 minutes | When facts change |

**Daily total: 13 minutes.**
**Weekly total: 65 minutes + 30 minutes (Sunday) = ~95 minutes per week.**

If a week of Lorraine OS takes less than 2 hours, it is not a burden. It is leverage.

---

## The Two Habits

**Habit 1 — Open Lorraine OS before email, Slack, or any reactive tool.**

Email and Slack are other people's priorities. Lorraine OS is yours. Open it first.

This is the habit that makes the system work. Without it, the morning startup never happens, the context drifts, and the system becomes an expensive folder of markdown files.

**Habit 2 — Sunday planning is non-negotiable.**

30 minutes on Sunday is the highest-return investment in the week. It transforms Monday from reactive to intentional.

If you miss a Sunday, do it Monday morning. Never miss two in a row.

---

## The Commit Protocol

Every session ends with one command:

```bash
git add -A
git commit -m "session: YYYY-MM-DD — [one sentence]"
```

This is not bureaucracy. This is your audit trail. After 90 days, you have 90 commits and a complete history of what you decided, what you worked on, and what changed. That history is the system's long-term memory.

---

## When to Add More

Add WELLBEING.md when: you are in a high-pressure period and want the capacity check in your session brief.

Add AI_ENGINEER.md when: you are in a technical work session and need architecture review.

Add COMMUNICATION.md when: you need to draft something important.

Add POSITIONING.md when: you are doing a quarterly career review or evaluating an opportunity.

**Add things when you feel their absence. Not before.**

---

## What Good Looks Like at 30 Days

- context.md updated at least 8 times
- 4 weekly plans created and reviewed
- At least 3 decisions in decisions_log.md
- At least 10 wins in wins_log.md
- Git history with 30+ commits
- You know your open questions without reading the file
- Sunday planning feels like a ritual, not a chore

---

## What Good Looks Like at 90 Days

- The session brief surfaces things you didn't consciously know you needed
- Decisions are faster because the framework is automatic
- Planning accuracy improves — your rocks are the right size
- Patterns are emerging in patterns.md
- The system has evolved: some files added, some removed, some rewritten
- You are building the MCP server (because now you know exactly what it needs to do)

---

## The Single Most Important Thing

Keep context.md accurate.

Everything else in Lorraine OS depends on this file. Stale context produces stale advice. Accurate context produces advice that is actually useful.

Every time something changes — a role, a project, a financial fact, a priority shift — update context.md that day.

That is the system. Everything else is a feature built on top of it.
