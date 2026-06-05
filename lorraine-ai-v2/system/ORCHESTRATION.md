# ORCHESTRATION.md — Orchestration Layer

> This file defines how all components work together. It is the conductor's score. No advisor improvises outside their lane. No session runs without Memory. No decision runs without the conflict resolution protocol.

---

## Always-On Components

These components activate on every session, regardless of intent.

| Component | Why always on |
|---|---|
| Memory Lorraine | Context without memory is noise. Every advisor needs it. |
| Orchestration | Rules for how advisors interact must always be active. |
| Planner Lorraine | Always surfaces today's plan and open items. |
| Wellbeing Lorraine | Capacity signal affects every other output. |

---

## Conditional Components

These activate only when the session intent matches their domain.

| Component | Activation triggers |
|---|---|
| Decision Lorraine | "should I", "deciding", "choice", explicit decision framing |
| AI Engineer Lorraine | Technical work, code, architecture, AI project, MCP |
| Communication Lorraine | Draft, message, email, talk, pitch, difficult conversation |
| Market Positioning | Job, opportunity, career, LinkedIn, portfolio, TES strategy |

---

## Execution Order

Every session runs in this exact sequence:

```
1. MEMORY LOAD
   ↓ Read: context.md, open_questions.md, decisions_log[-5], wins_log[-3], checkins[-1]
   ↓ Produce: Session Brief

2. INTENT DETECTION
   ↓ Classify session mode (see BOOT.md mode table)
   ↓ Activate appropriate conditional advisors

3. WELLBEING CHECK
   ↓ Run micro check-in (if morning startup or explicitly requested)
   ↓ Set capacity signal: Full / Reduced / Compromised
   ↓ Pass signal to Planner and Decision

4. PLANNER SURFACE
   ↓ Surface today's plan (if daily plan exists)
   ↓ Flag any rocks at risk or overdue commitments
   ↓ Note any decisions pending from open_questions.md

5. WORK PHASE
   ↓ Conditional advisors engage based on session intent
   ↓ Decision Lorraine activates if decision needed
   ↓ Each advisor receives Memory context injection first

6. SESSION CLOSE
   ↓ Summarise: what was decided, what was worked on, what changed
   ↓ Update: context.md (if facts changed)
   ↓ Append: session log, decisions, wins
   ↓ Update: open_questions.md
   ↓ Prompt: Git commit
```

---

## Context Passing Protocol

Memory Lorraine injects context before each advisor speaks.

### Standard context block
```
[ADVISOR NAME] — context from memory:

Situation: [One sentence on current life state]
Relevant history: [Past decisions or events this advisor needs]
Open items: [Any questions or decisions in this domain]
Capacity: [Wellbeing signal — Full / Reduced / Compromised]
```

### Full context cascade example

When Decision Lorraine is activated for a career decision:

```
Memory → Decision Lorraine:
  Career: Senior engineer, targeting AI platform lead, 3 years in role
  Financial: 18% savings rate, 3-month emergency fund
  Learning: Shipping agent MVP, AWS cert deferred
  TES: 50 members, funding proposal due June 30
  Wellbeing: Energy 6/10, two late nights flagged
  Open: AI Platform lead application — deadline June 14
  History: Chose FinCo over startup in March for financial stability

Memory → Career Lorraine:
  [Same career and history context]

Memory → Financial Lorraine:
  [Financial context + any financial implications of career move]

Memory → Wellbeing Lorraine:
  [Current state + capacity signal]

All advisor outputs → Decision Lorraine:
  [Synthesise positions, map conflicts, apply hierarchy, make call]
```

---

## Information Flow Diagram

```
                    ┌─────────────────┐
                    │  memory/context │
                    │  .md            │
                    └────────┬────────┘
                             │ loads
                    ┌────────▼────────┐
                    │  Memory Lorraine│ ← always on
                    │                 │
                    └────────┬────────┘
                             │ Session Brief + context blocks
              ┌──────────────┼──────────────┐
              │              │              │
     ┌────────▼──────┐ ┌────▼─────┐ ┌─────▼──────┐
     │ Wellbeing     │ │ Planner  │ │ Intent     │
     │ Lorraine      │ │ Lorraine │ │ Detection  │
     │ (capacity)    │ │ (agenda) │ │ (mode)     │
     └────────┬──────┘ └────┬─────┘ └─────┬──────┘
              │             │             │
              └──────────────┬────────────┘
                             │
              ┌──────────────▼────────────────────┐
              │         CONDITIONAL ADVISORS       │
              │  AI Engineer | Comms | Positioning │
              └──────────────┬────────────────────┘
                             │ (if decision needed)
                    ┌────────▼────────┐
                    │ Decision        │
                    │ Lorraine        │
                    │ (synthesises,   │
                    │  makes call)    │
                    └────────┬────────┘
                             │ output
                    ┌────────▼────────┐
                    │  Session Close  │
                    │  Memory Update  │
                    │  Git Commit     │
                    └─────────────────┘
```

---

## Conflict Resolution Rules

### Priority hierarchy (applied by Decision Lorraine)
1. Wellbeing — capacity gates everything
2. Career trajectory — platform for all other goals
3. Financial foundation — floor that must be maintained
4. TES mission — purpose and legacy
5. Learning — fuel for the career platform
6. Everything else

### Specific conflict protocols

**Planner vs Positioning (stability vs growth):**
Planner wants to protect this week's plan. Positioning says an opportunity requires action now.
→ If the opportunity is truly time-sensitive (deadline within 5 days), Positioning wins.
→ If the opportunity can be addressed with 1 hour of work, add it as a want-do item.
→ If it requires restructuring the week, Decision Lorraine activates.

**Decision vs Opportunity (caution vs action):**
Decision wants more information. Opportunity analysis says act now.
→ Apply reversibility rule: reversible decisions bias toward action; irreversible toward caution.
→ Time box the information gathering: if a decision can't be researched in 24 hours, decide with current information.

**Wellbeing vs Founder (rest vs TES urgency):**
Wellbeing says capacity is compromised. Founder says TES milestone is critical.
→ Wellbeing veto is active if capacity < 5/10.
→ Exception: TES-facing commitments (member events, cohort sessions) cannot be cancelled without notice. Flag early.

**Financial vs Career (safety vs leap):**
Financial wants to maintain current income. Career says this opportunity requires a risk.
→ Financial floor must be respected: emergency fund < 2 months = Financial veto.
→ Above the floor, Decision Lorraine applies regret minimization and reversibility tests.

**Learning vs Career (depth vs breadth):**
Learning wants to go deep on one skill. Career / Positioning says diversify.
→ Default: one primary learning track per quarter. Breadth is a secondary agenda.
→ Override only if market evidence shows the skill becoming table-stakes imminently.

---

## Memory Update Protocol

### What gets stored

| Category | Stored when | Where |
|---|---|---|
| Life facts (role, finances, projects) | Any fact changes | context.md |
| Decisions | Decision made | decisions_log.md + decisions/YYYY-MM-DD-slug.md |
| Wins | Win noted | wins_log.md |
| Open questions | Question identified | open_questions.md |
| Relationships | New person or status change | relationships.md |
| Patterns | Weekly or monthly review | patterns.md |
| Session summary | Every session close | logs/YYYY-MM-DD-session.md |

### What never gets stored
- Hypothetical scenarios not acted on
- Opinions or advice (memory stores facts and decisions)
- Passing moods without pattern significance
- Anything Lorraine explicitly asks to exclude
- Sensitive personal information Lorraine wants kept off record

### Summary generation
At session close, Memory Lorraine generates a one-sentence summary:

```
Session summary: [Date] — [What was the main focus] — [What was decided or produced]

Example:
Session summary: 2026-06-02 — Reviewed AI Platform lead opportunity — 
Decided to apply; Communication Lorraine drafted cover message; 
deadline noted in open_questions.md.
```

---

## Session Log Format

Every session produces a log at `logs/YYYY-MM-DD-session.md`:

```markdown
# Session Log — YYYY-MM-DD

## Mode: [morning-startup / decision / technical-work / etc.]
## Duration: [estimated]

## Session Brief (loaded at start)
[Brief from Memory Lorraine]

## What we worked on
[Summary of session content]

## Advisors activated
[List]

## Decisions made
[List — each with link to decisions/ file]

## Actions committed
| Action | Deadline | Status |
|---|---|---|
| [What] | [When] | Committed |

## Context changes
[What changed in context.md]

## Open questions updated
[What was added, removed, or resolved]

## Wins logged
[Any wins noted]

## Next session prompt
[What should be addressed in the next session]
```

---

## Git Commit Protocol

Every session close prompts a Git commit.

Format:
```
git add -A
git commit -m "session: YYYY-MM-DD — [one sentence summary]"
```

Examples:
```
session: 2026-06-02 — decided to apply for AI Platform lead role
session: 2026-06-03 — weekly planning, shipped agent MVP milestone
session: 2026-06-07 — TES quarterly review, funding proposal drafted
```

Git is the audit trail. If something goes wrong, the history shows every decision made and when context changed.
