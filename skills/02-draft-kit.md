# Skill 02 — Draft Kit

**Invocation:** `/kit-draft`

**Purpose:** Read the grill output and produce a `kit-manifest.md` — the full spec of the kit before any files are written. The manifest is the agreement. Nothing gets built until it's approved.

**Output:** `kit-manifest.md` written to the current working directory.

---

## Before You Start

1. Check that `grill-output.md` exists. If it doesn't, tell the user to run `/kit-grill` first.
2. Read `grill-output.md` completely before writing anything.
3. Check whether `kit-manifest.md` already exists. If it does, ask: "Do you want to revise the existing manifest or start a new one?"

---

## Drafting Protocol

Do not write the manifest silently. Build it section by section and confirm as you go.

### Step 1 — Name and Purpose

Propose a kit name and a one-sentence purpose statement. Ask:
> "Does this name and purpose match what you're building?"

The name should be `[domain]-kit` style (e.g., `jobs-kit`, `learning-kit`, `contracts-kit`).

### Step 2 — User Persona Section

From the grill, write a 3-5 sentence persona that Claude will read at the start of every session in this kit. It should cover:
- Who the user is
- What they already know (so Claude doesn't over-explain)
- Their preferences and constraints
- Their deal-breakers

Show it and ask: "Is there anything here that's wrong or missing?"

### Step 3 — Task Inventory

List every discrete task surfaced in the grill. For each task, fill in:

```
Task: [name]
Input: [what comes in]
Output: [what goes out]
Destination: [where the output goes]
Skill file: skills/[NN]-[task-slug].md
```

Show the full list and ask: "Are these the right tasks? Anything missing or wrong?"

### Step 4 — Workflow Map

For each workflow sequence, write a numbered list of steps with decision points. Use this format:

```
Workflow: [name]
1. [Step] → Input: X, Output: Y
2. [Decision] — If A, go to step 3. If B, go to step 5.
3. [Step] → ...
```

Show each workflow and ask: "Does this sequence match how this actually works?"

### Step 5 — Context Files

List every reference file the kit needs. For each:

```
File: [filename]
Contents: [what goes in it]
Loaded by: [which skills read it]
Created by: [user fills it in / Claude generates it / pulled from existing file]
```

### Step 6 — Template Inventory

List every artifact the kit produces that needs a template. For each:

```
Template: templates/[name].md
Produced by: [which skill]
Used by: [user / next skill / external destination]
```

### Step 7 — Directory Layout

Propose the full directory structure of the kit. Use the standard anatomy from `docs/kit-anatomy.md`.

### Step 8 — Lessons Log

Confirm that the kit will include a `lessons-log.md`. Seed it with any lessons-so-far from the grill (Area 6). If none, create an empty log with the right structure.

---

## Finalizing the Manifest

Write `kit-manifest.md` using `templates/kit-manifest.md` as the base. Then say:

> "Here's the full manifest. Read through it — especially the workflow maps and the task inventory. Tell me what's wrong before I write a single file."

Wait for explicit approval. "Looks good" counts. "Whatever" does not — push back:
> "I want to make sure this is right before I build. Is there anything you'd change?"

Once approved, say:
> "Manifest locked. Run `/kit-actualize` when you're ready to build."
