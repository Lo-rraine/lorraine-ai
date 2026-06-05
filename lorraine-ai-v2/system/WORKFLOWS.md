# WORKFLOWS.md — Operational Workflows

> Exact workflows for daily, weekly, monthly, and quarterly operation of Lorraine AI v2. These are not suggestions. They are the operating system's scheduled processes.

---

## Daily Workflow

### Morning Startup (15 minutes)

**When:** Before starting work. Every workday.
**Boot command:** `"Boot Lorraine AI. Run morning startup."`

**Sequence:**

```
1. Memory loads context and produces Session Brief
2. Wellbeing micro check-in (rate 4 currencies 1-10)
3. Planner surfaces today's plan
4. Review: any rocks from yesterday incomplete?
5. Confirm or adjust today's plan based on energy mode
6. Name one thing that makes today a success
7. Start
```

**Output:** `plans/daily/YYYY-MM-DD.md` (created or confirmed)

**Time check:** If this is taking more than 20 minutes, Planner is too complex. Simplify.

---

### Workday Operation

**During the day, Lorraine AI operates in these modes:**

| Situation | What to do |
|---|---|
| Stuck on a technical problem | `"Boot AI Engineer Lorraine. I'm stuck on [problem]."` |
| Drafting important message | `"Boot Communication Lorraine. I need to write [message]."` |
| Career decision surfaced | `"Boot Lorraine AI. Decision session — [topic]."` |
| Energy crash mid-day | `"Boot Wellbeing Lorraine. Check-in."` |
| Idea or win to capture | `"Log this to Lorraine AI: [idea/win]."` |

**Capture anything that matters immediately.** The system only knows what you tell it.

---

### Evening Reflection (10 minutes)

**When:** End of workday. Not optional.
**Boot command:** `"Boot Lorraine AI. End of day."`

**Sequence:**

```
1. Mark rocks complete or incomplete in today's daily plan
2. Log any wins from today
3. Note any decisions made
4. Update open_questions.md if new questions surfaced
5. One sentence: what did today teach me?
6. Session close — Memory updates, Git commit
```

**If too tired for the full reflection:** Minimum viable close:
```
"End session. Today I [completed / worked on]. No decisions made. Commit."
```

---

## Weekly Workflow

### Sunday Planning (30 minutes)

**When:** Sunday evening.
**Boot command:** `"Boot Lorraine AI. Sunday planning session."`

**Sequence:**

```
1. Memory loads context and last week's plan
2. Planner: review last week
   - What rocks completed?
   - Completion rate?
   - What didn't get done and why?
   - Any patterns to note?
3. Planner: set this week
   - Theme (one sentence)
   - 3 rocks maximum
   - Learning block (hours and goal)
   - TES commitment
   - Recovery plan
   - Explicit exclusions
4. Decision check: any open questions that need a decision this week?
5. Wellbeing: energy assessment for the week
6. Produce and save plans/weekly/YYYY-Www.md
7. Git commit
```

**Output:** `plans/weekly/YYYY-Www.md`

---

### Friday Review (20 minutes)

**When:** Friday afternoon.
**Boot command:** `"Boot Lorraine AI. Friday review."`

**Sequence:**

```
1. Open this week's plan
2. Mark each rock complete / incomplete
3. Calculate completion rate
4. Planner review questions:
   - What worked?
   - What didn't?
   - What was the quality of work this week?
   - Is energy higher or lower than Monday?
5. Wellbeing weekly review
6. Pattern check: did any pattern from patterns.md appear this week?
7. Update open_questions.md
8. Note anything for Sunday planning
9. Session close and commit
```

**Output:** Updated weekly plan file with completion marks + session log

---

## Monthly Workflow

### Monthly Review (45 minutes)

**When:** Last day of month or first day of next month.
**Boot command:** `"Boot Lorraine AI. Monthly review — [Month YYYY]."`

**Sequence:**

```
1. Memory loads full context
2. Review all four weekly plans from the month
   - Average rock completion rate
   - Learning block completion rate
   - Patterns observed
3. Positioning: career checkpoint (30-minute version)
   - Progress toward trajectory
   - Market position change?
   - Portfolio additions?
4. Financial: monthly financial review
   - Savings rate actual vs target
   - Any changes to financial picture
   - Financial action for next month
5. TES: monthly milestone review
   - What was accomplished
   - What's next
6. Wellbeing: monthly pattern review
   - Average scores
   - Trends
   - Recommendations for next month
7. Produce plans/monthly/YYYY-MM.md
8. Update memory/patterns.md
9. Git commit
```

**Output:** `plans/monthly/YYYY-MM.md`, updated `memory/patterns.md`

---

## Quarterly Workflow

### Quarterly Review and Planning (2 hours)

**When:** First week of each new quarter.
**Boot command:** `"Boot Lorraine AI. Quarterly review and planning — Q[n] YYYY."`

**Sequence:**

```
1. REVIEW PHASE (60 minutes)
   a. Load all three monthly plans from the quarter
   b. Score each OKR key result: 0.0 – 1.0
   c. Market Positioning: full career review
   d. Financial: quarterly financial assessment
   e. Wellbeing: quarterly pattern analysis
   f. Decision: retrospective on any major decisions made
   g. Identify 3 patterns that defined the quarter
   h. Update memory/patterns.md with quarterly observations

2. PLANNING PHASE (60 minutes)
   a. Planner: set quarterly OKRs (all domains)
   b. Activate all relevant advisors for input
   c. Decision Lorraine: resolve any OKR conflicts
   d. Set the quarterly theme (one sentence)
   e. Identify the 3 bets for the quarter
   f. Name explicit quarterly exclusions
   g. Produce plans/quarterly/YYYY-Qn.md

3. SESSION CLOSE
   a. Update context.md with any changed facts
   b. Commit with message: "quarterly: Q[n] YYYY review and planning"
```

**Output:** `plans/quarterly/YYYY-Qn.md`, updated `memory/patterns.md`, updated `memory/context.md`

---

## Annual Workflow

### Annual Review and Planning (Half day)

**When:** December or first week of January.
**Boot command:** `"Boot Lorraine AI. Annual review — YYYY."`

**Sequence:**

```
1. REVIEW (2 hours)
   a. Review all four quarterly plans
   b. Review annual OKRs / bets
   c. Score each: achieved / partial / missed
   d. Market Positioning: year-in-review on career trajectory
   e. Financial: year-in-review financial assessment
   f. TES: year-in-review for the organisation
   g. Wellbeing: year-in-review on energy and resilience
   h. Learning: what expertise was built this year?
   i. What were the 3 most important decisions of the year?
   j. What were the 3 most important lessons?
   k. What would you tell January-you?

2. PLANNING (2 hours)
   a. Set the annual theme for next year
   b. Name the 3 bets for next year
   c. Set annual directional goals (not detailed — quarterly OKRs handle detail)
   d. Name explicit annual exclusions
   e. Produce plans/annual/YYYY.md

3. CLOSE
   a. Full context.md update
   b. Update memory/patterns.md with annual observations
   c. Commit with message: "annual: YYYY review and YYYY+1 planning"
```

---

## Learning System — Continuous Improvement Loops

### Session-level learning loop

Every session, Memory Lorraine checks:
- Did we make a decision with a `review_date`? If due, surface for retrospective.
- Did we commit to an action? Is it complete?
- Did an advisor make a recommendation that was acted on? What was the outcome?

### Weekly learning loop

Every Friday review:
- Were the rocks achievable? (if < 50% completion, rocks were too many or too large)
- Was the planning session accurate? (did the week unfold as planned?)
- What adjusted the plan? (surface as pattern if recurring)

Planner Lorraine calibrates rock size and count based on historical completion rate.

### Monthly learning loop

Every monthly review:
- OKR vs actual: where was planning accurate? Where was it wrong?
- Update patterns.md with any recurring themes
- Update advisor behaviour: if a type of decision keeps being wrong, note the failure mode

### Decision learning loop

Every decision with a `review_date`:
- Was the decision right? (factual outcome assessment)
- Was the reasoning right? (even if outcome was wrong — did we reason well?)
- What would we decide differently?
- Does this change any advisor's default position? (update relevant skill file if so)

### Advisor calibration

Quarterly, during the planning phase:
- Which advisor has been most useful this quarter?
- Which advisor has given advice that was consistently wrong?
- Which advisor's output is least trusted?

Wrong advisors get updated in their `.md` file. The system improves because the markdown improves.

---

## Knowledge Accumulation Strategy

Lorraine AI v2 accumulates knowledge in three ways:

**1. Decisions log** — what was decided and what actually happened. Over 12 months this becomes a calibrated decision history. Patterns emerge. Advisor accuracy improves.

**2. Patterns file** — recurring themes extracted from weekly/monthly reviews. This is the system's explicit learning. It doesn't happen automatically — it happens when Lorraine and the system notice something and name it.

**3. Advisor files** — the `.md` skill files are not frozen. They evolve. If Communication Lorraine consistently misunderstands Lorraine's voice, update COMMUNICATION.md. If AI Engineer Lorraine's simplicity heuristics are wrong for a specific domain, update AI_ENGINEER.md. The system improves by editing the files that define it.

**The compounding effect:** After 6 months, a session brief from Memory Lorraine contains 6 months of decisions, patterns, and wins. The advisors have been updated based on what worked and what didn't. The plans are calibrated to actual completion rates. This is a meaningfully different system from month one.
