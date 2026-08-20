# Skill 04 — Lessons Learned

**Invocation:** `/kit-lessons`

**Purpose:** Apply real-world learnings to the actualized kit. Revises skill files, templates, and AGENTS.md based on what's been learned in use. The kit-builder itself is never touched.

**Output:** Revised files inside the actualized kit. A new entry in `lessons-log.md`.

---

## Before You Start

1. Ask the user which kit they're revising and where it lives:
   > "Which kit are we updating, and where is it? (e.g., `/Users/you/Desktop/kits/jobs-kit`)"
2. Read `lessons-log.md` from that kit. Understand what's already been applied.
3. Read `AGENTS.md` from that kit. Understand the current state.

---

## Intake Protocol

Do not ask the user to fill out a form. Ask:

> "Tell me what you learned. What broke, what was awkward, or what surprised you?"

Then probe:
- "Where in the workflow did this happen?"
- "What did you expect vs. what actually happened?"
- "Was this a one-time edge case or does it happen regularly?"
- "What would the fixed version have done instead?"

Repeat until you have concrete, actionable learnings — not vague impressions.

---

## Classifying Learnings

Sort each lesson into one of these categories:

| Type | What it means | Where to fix it |
|---|---|---|
| **Wrong output shape** | The skill produced the right content but in the wrong format | Skill file — revise the Output section |
| **Missing context** | Claude didn't know something it needed | AGENTS.md or a context/docs file |
| **Wrong sequence** | Steps were in the wrong order, or a step was missing | Skill file — revise the Steps section |
| **Bad assumption** | Claude assumed something that wasn't true for this user | AGENTS.md — add to Hard Constraints |
| **New task needed** | A whole new workflow or task was discovered | New skill file + update AGENTS.md index |
| **Template gap** | The template didn't have a field that turned out to be needed | Template file — add the field |
| **Edge case** | A specific situation the skill didn't handle | Skill file — add a decision point |

Tell the user how you've classified each lesson before making any changes.

---

## Making Changes

For each lesson:

1. State what file you're changing and why.
2. Make the change.
3. Read the changed section back to the user.
4. Ask: "Does that fix it?"

Do not batch changes silently. Surface each one.

---

## Updating the Lessons Log

After all changes are applied, add an entry to `lessons-log.md`:

```
## [Date] — [Session title or context]

### What was learned
[2-4 sentences describing the experience that produced the lesson]

### What was changed
- [File]: [what changed and why]
- [File]: [what changed and why]

### Still open
[Anything that came up but wasn't resolved — questions, edge cases, things to watch]
```

---

## Closing

Say:
> "Changes applied. [N] files updated, [N] lessons logged."

If anything came up during the session that might require a deeper re-grill (e.g., a whole new workflow was discovered, or the user's needs have significantly shifted), say:
> "Some of what came up suggests the kit's structure might need rethinking, not just patching. Consider running `/kit-re-grill` to go deeper."
