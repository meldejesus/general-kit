# Skill 01 — Grill

**Invocation:** `/kit-grill`

**Purpose:** Interview the user deeply enough that you can build a kit that actually serves them. One question at a time. No assumptions. No rushing to the manifest.

**Output:** `grill-output.md` written to the current working directory.

---

## Before You Start

Check whether a `grill-output.md` already exists. If it does, read it and ask:

> "I see a previous grill session. Do you want to continue from where we left off, start fresh, or run a targeted re-grill on a specific area?"

If starting fresh, delete or archive the old file.

---

## Grill Protocol

Ask questions **one at a time**. After each answer:
- Probe if the answer is vague, broad, or skips over something important
- Reflect back what you heard if there's a hidden assumption worth surfacing
- Move to the next area only when you have a concrete, usable answer

Do not summarize at the end of each answer. Just probe or move on.

---

## Area 1 — The Person

Goal: understand who is using this kit and what they already know.

Start with:
> "Tell me what you do — not your job title, but the actual work you're doing day to day."

Probe for:
- Domain (coding, writing, research, sales, legal, ops, creative, etc.)
- Experience level with Claude Code (never used it / uses it daily)
- Whether they're building this kit for themselves or for someone else
- What tools or systems they're already working inside (Notion, GitHub, Slack, a CRM, raw files, etc.)

Move on when you know: who they are, what they do, and what environment they work in.

---

## Area 2 — The Repeated Work

Goal: find the tasks that happen over and over and are currently painful or slow.

Ask:
> "What's the work you do most often that you wish was faster or more consistent?"

Probe for:
- Frequency (daily, weekly, per project, per client)
- Whether the task is always the same or varies each time
- What the input is (a document, a URL, a spreadsheet, a conversation, raw notes)
- What the output is (a file, a message, a decision, a report, an action)
- Where the output goes (sent to someone, saved somewhere, fed into the next step)

Repeat this area until you have at least 2-3 distinct repeated tasks. Ask:
> "What else do you do that fits that pattern?"

Move on when you have a concrete list of repeated tasks with inputs, outputs, and destinations.

---

## Area 3 — The Workflows

Goal: find the sequences — the multi-step jobs that chain tasks together.

Ask:
> "Walk me through the last time you completed one of these tasks start to finish. What actually happened, in order?"

Probe for:
- Decision points (where does the work branch based on what you find?)
- Handoffs (where does something leave Claude and go somewhere else?)
- Failure modes (where does this usually go wrong or get stuck?)
- Context Claude would need but doesn't have upfront (data files, personal preferences, domain knowledge)

Repeat for each major workflow. Ask:
> "Is there a sequence where these tasks connect — where the output of one feeds into the next?"

Move on when you can draw the workflow as a sequence of steps with decision points.

---

## Area 4 — The Context Problem

Goal: find what Claude needs to know upfront to do good work in this domain.

Ask:
> "When you've used Claude for this kind of work before, where did it go wrong? What did it not know?"

Probe for:
- Personal or organizational context (who you are, your preferences, constraints, deal-breakers)
- Domain knowledge Claude needs (terminology, rules, exceptions, edge cases)
- Reference files that should always be loaded (a profile, a style guide, a list of companies, a rubric)
- Things Claude tends to assume that are wrong for this person

Move on when you know: what context files the kit needs, and what Claude must never assume.

---

## Area 5 — The Output Contract

Goal: define what done looks like for each task.

Ask:
> "Show me an example of what a perfect output looks like for one of these tasks. Or describe it in enough detail that I could write a rubric."

Probe for:
- Format (structured markdown, plain prose, table, JSON, a file, a message)
- Length and density expectations
- Tone if it's human-facing
- What makes an output useful vs. technically correct but useless
- Whether outputs are saved to files, sent somewhere, or reviewed inline

Repeat for each major task.

Move on when every task has a defined output shape.

---

## Area 6 — The Lessons So Far

Goal: capture what the user already knows from experience.

Ask:
> "If you've run any version of this workflow before — even manually or with a different tool — what did you learn the hard way?"

Probe for:
- What almost worked but didn't
- Edge cases that broke the process
- Decisions that seemed obvious but turned out to be wrong
- Anything they'd tell a new person joining the workflow on day one

Move on when you've captured at least one concrete lesson (or confirmed there's no prior experience to pull from).

---

## Closing the Grill

When all six areas are covered, say:

> "I have what I need. Let me write the grill output. I'll read it back to you — push back on anything that's wrong or missing."

Write `grill-output.md` using the template at `templates/grill-output.md`. Then read back the key findings in plain language — not the file, just a 5-6 sentence summary. Ask:

> "Does that match what you had in mind? Anything I missed or got wrong?"

Apply any corrections to `grill-output.md` before closing.

---

## What Comes Next

Tell the user:
> "Run `/kit-draft` when you're ready — I'll build the kit manifest from this."
