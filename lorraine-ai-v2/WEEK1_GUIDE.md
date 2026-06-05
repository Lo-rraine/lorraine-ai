# Lorraine OS — First Week Usage Guide

> Day-by-day onboarding. This is about usage, not architecture. Follow it exactly.

---

## Day 1 — Setup (60 minutes)

### Goal: The system exists and context.md is filled in.

**Step 1 — Create the folder (5 minutes)**

```bash
# If you downloaded the zip:
unzip lorraine-os.zip
cd lorraine-ai-v2
git init
git add -A
git commit -m "init: Lorraine OS — day 1"
```

**Step 2 — Fill in context.md (30 minutes)**

Open `memory/context.md`. This is the most important thing you do today.

Fill in every section honestly. Specifically:
- Your actual current role, company, team
- Your actual financial numbers (savings rate, emergency fund status)
- Your actual learning track and current project
- Your actual TES status
- Your real top 3 priorities right now

Do not leave template placeholders. Replace every `[bracket]` with your real situation.

**This file is the brain. If it's vague, the system is vague.**

**Step 3 — Fill in open_questions.md (10 minutes)**

Write down every decision you're sitting with right now. All of them. Even the ones you've been avoiding.

Format:
```
- [ ] [Question] — added YYYY-MM-DD — urgency: high/medium/low
```

**Step 4 — Write one win (5 minutes)**

Open `memory/wins_log.md`. Add one real win from the last two weeks.

This is not optional. The wins log exists because humans have selective memory for failure and amnesia for success. Start the record now.

**Step 5 — Commit (5 minutes)**

```bash
git add -A
git commit -m "session: day-1 — context.md populated, system initialised"
```

**Step 6 — Do not build anything else today.**

Day 1 is done. The system is running. You used it.

---

## Day 2 — First Session (20 minutes)

### Goal: Run your first real morning startup.

**Morning (10 minutes)**

Open Claude Code. Paste this exactly:

```
Read these files:
- memory/context.md
- memory/open_questions.md
- memory/wins_log.md (last entry only)
- plans/weekly/ (today is [DATE], what week is this?)

You are running as Lorraine OS. Give me:
1. A 5-line session brief: last session, open decisions, current priorities, one win, one watch item.
2. Suggest 3 rocks for today based on my open questions and context.
```

Read the output. Adjust the rocks to match what you actually need to do today.

Write today's rocks in `plans/daily/YYYY-MM-DD.md` (you can copy the template).

**That is a session. You ran the system.**

**Evening (5 minutes)**

Open today's daily plan. Mark what you completed. Paste into Claude Code:

```
End of session. Today I completed [list]. 
Update wins_log.md if anything qualifies.
What should I note for tomorrow?
```

Commit:
```bash
git add -A
git commit -m "session: YYYY-MM-DD — first full session"
```

---

## Day 3 — Memory Update (15 minutes)

### Goal: Practise keeping context.md current.

Something changed since Day 1. It always does.

**Morning**

Before starting work, open `memory/context.md` and ask: is anything here stale or wrong?

Look specifically at:
- Commitments with deadlines — are the statuses accurate?
- Current top 3 priorities — do these still reflect reality?
- Open questions — has anything been resolved? Are there new ones?

Update whatever is wrong. Even one sentence.

**Then paste into Claude Code:**

```
Read memory/context.md (I just updated it).
What is the most important thing I should be paying attention to today?
```

This is memory in action. The system knows more than yesterday because you updated it.

**Commit:**
```bash
git add -A
git commit -m "session: YYYY-MM-DD — context updated"
```

---

## Day 4 — First Decision Session (30 minutes)

### Goal: Run the decision protocol on a real open question.

Pick one item from `memory/open_questions.md`. The one you've been avoiding is the right choice.

**Paste into Claude Code:**

```
Read these files:
- system/DECISION.md
- memory/context.md
- memory/open_questions.md

I need to run a decision session on: [paste the question]

Follow the full Decision Lorraine protocol:
1. Frame the decision precisely
2. Surface relevant advisor positions (Career, Financial, Wellbeing, Future — as relevant)
3. Map any conflicts
4. Apply the value hierarchy
5. Run the appropriate tests (regret minimization, pre-mortem, reversibility)
6. Make a single unambiguous recommendation
7. Name the first action and the review trigger

Do not hedge. Make the call.
```

Read the output. Do you agree? Disagree with one advisor's position? Say so.

When you have a final decision, save it:

```bash
# Copy the decision output to:
decisions/YYYY-MM-DD-[slug].md
```

Update `memory/open_questions.md` — mark that question resolved.
Update `memory/decisions_log.md` — add the new entry.

**Commit:**
```bash
git add -A
git commit -m "decision: YYYY-MM-DD — [what was decided]"
```

---

## Day 5 — Planning Session (30 minutes)

### Goal: Create next week's plan before the weekend.

It is Thursday or Friday. Do this before the weekend, not during it.

**Paste into Claude Code:**

```
Read these files:
- system/PLANNER.md
- memory/context.md
- memory/open_questions.md
- plans/weekly/ (find this week's file)

Run a weekly planning session.

Tell me:
1. Did I complete this week's rocks? (I completed: [list what you actually did])
2. What is the theme for next week?
3. What are next week's 3 rocks? (pull from context.md priorities and open_questions.md)
4. What is the learning block — specific goal and project?
5. What am I explicitly NOT doing next week?
6. What decision is pending that needs to be made next week?
```

Save the output to `plans/weekly/YYYY-Www.md`.

**This is the highest-value habit in the system.** Everything else is infrastructure for this moment.

**Commit:**
```bash
git add -A
git commit -m "plan: week [Ww] — [theme]"
```

---

## Day 6 — First Review (20 minutes)

### Goal: Close the week honestly.

Open this week's plan. Go through each rock:

- Complete? Mark it `[x]`
- Incomplete? Mark it `[ ]` with a note: why not?

Calculate completion rate: N of 3 rocks done.

**Paste into Claude Code:**

```
Read plans/weekly/[this week].md and memory/context.md.

Weekly review:
- I completed [N] of 3 rocks.
- What I completed: [list]
- What I didn't complete: [list] because [honest reason]
- Energy this week felt: [1-10]

Tell me:
1. What does my completion rate say about my planning accuracy?
2. Was the rock size right or were they too large?
3. What one thing should I change in next week's plan?
4. Is there any pattern forming?
```

Note what comes back. If a pattern is forming, add it to `memory/patterns.md`.

**Commit:**
```bash
git add -A
git commit -m "review: week [Ww] — [completion rate], [one sentence on what you learned]"
```

---

## Day 7 — First Weekly Review (30 minutes)

### Goal: Make the Sunday planning session a permanent habit.

Today is Sunday. This is the most important thing you do this week.

**Do not skip it. Do not shorten it. Do it before the week starts.**

**Paste into Claude Code:**

```
Read these files:
- system/PLANNER.md
- memory/context.md
- memory/open_questions.md
- memory/wins_log.md
- plans/weekly/[last week]

You are Planner Lorraine running the Sunday planning session.

1. First, review last week: what happened, what didn't, what the completion rate tells us.
2. Surface any open decisions from open_questions.md that need attention this week.
3. Set next week's theme in one sentence.
4. Choose 3 rocks. No more. Pull from context.md priorities.
5. Assign learning block: specific goal, specific project, specific hours.
6. Name TES commitment for the week.
7. Name explicit exclusions — what we're NOT doing.
8. Flag any decisions that need a Decision Lorraine session this week.

Output: complete weekly plan ready to save.
```

Save the output. Read it. Ask yourself: is this the week I actually want to have?

If yes — commit and start Monday with intention.
If no — adjust and recommit.

**Commit:**
```bash
git add -A
git commit -m "plan: week [Ww] — [theme]"
```

---

## End of Week 1 — What You Should Have

```
✅ context.md — filled in, accurate, updated at least once
✅ open_questions.md — live, questions resolved where possible
✅ wins_log.md — at least 2 entries
✅ decisions_log.md — at least 1 entry
✅ plans/weekly/ — 2 weekly plans (this week + next week)
✅ plans/daily/ — at least 3 daily plans
✅ decisions/ — at least 1 decision file
✅ logs/ — git history with 7+ commits
✅ Two habits installed: morning startup + Sunday planning
```

---

## What You Should NOT Have Built Yet

```
❌ MCP server
❌ Automation scripts
❌ Wellbeing scoring dashboard
❌ Patterns analysis
❌ Monthly review
❌ Quarterly OKRs
❌ Any technical infrastructure
```

**If you built any of the above, you built the wrong thing.**

Use the system. Build it second.
