# Skill 03 — Actualize

**Invocation:** `/kit-actualize`

**Purpose:** Read the approved `kit-manifest.md` and write all kit files. The kit lands in a directory you specify.

**Output:** A fully-structured kit directory, ready to use.

---

## Before You Start

1. Check that `kit-manifest.md` exists. If not, tell the user to run `/kit-draft` first.
2. Check that `grill-output.md` exists. You will need it for context the manifest may not repeat.
3. Ask the user where the kit should be created:
   > "Where should I write the kit? (e.g., `/Users/you/Desktop/kits/my-kit`)"
4. Confirm the target path does not already exist, or ask what to do if it does.

---

## Build Order

Write files in this order. Do not skip steps.

### 1. Create the directory structure

```
{kit-name}/
  AGENTS.md
  README.md
  skills/
  templates/
  docs/
  lessons-log.md
```

Create any additional directories named in the manifest.

### 2. Write `AGENTS.md`

This is the most important file. Claude reads it at the start of every session.

Include:
- Who Claude is in this kit (the persona)
- The user persona (from manifest Section 2)
- The full skill index with invocations and one-line descriptions
- What context files to read at the start of each session
- Hard constraints (what Claude must never do in this kit)
- What good output looks like in this domain

Do not write a generic AGENTS.md. Every line should be specific to this kit.

### 3. Write `README.md`

Human-facing. Cover:
- What the kit does in 2-3 sentences
- The workflow sequence (Skill 1 → Skill 2 → etc.) with what each produces
- Key files table
- Quick start steps

Keep it short. The AGENTS.md is for Claude; the README is for the human.

### 4. Write each skill file

For each task in the manifest, write `skills/NN-task-name.md`.

Every skill file must include:
- **Invocation** — the slash command
- **Purpose** — one sentence
- **Input** — what the skill expects (files, pasted content, user prompt)
- **Steps** — numbered, concrete, with decision points called out
- **Output** — exactly what gets written or returned, in what format
- **What comes next** — which skill to run after this one

Do not write skills that just say "analyze X and return results." Write skills that say exactly how to analyze, what to look for, how to structure the output, and what to do when something is ambiguous.

### 5. Write each template

For each template in the manifest, write `templates/template-name.md`.

Templates should be:
- Fillable — use `[PLACEHOLDER]` for fields Claude or the user fills in
- Structured — use consistent headers that other skills can navigate
- Self-labeling — include a comment at the top explaining what this template is and which skill produces it

### 6. Write context/docs files

For each file in the manifest's context file list:
- If the file should be filled in by the user: write it with clear placeholder instructions
- If Claude generates it: write a generation instruction block at the top of the file explaining how to create it
- If it comes from an existing file: write a note explaining the expected format

### 7. Write `lessons-log.md`

Seed with any lessons captured in the grill (Area 6). Use the structure from `templates/lessons-log.md`.

If no lessons yet, write the empty template with a note: "Add entries here after real-world use. Run `/kit-lessons` to apply them."

---

## After Writing

List every file created. Then say:

> "Kit is built. Here's what to do next:
> 1. Fill in any `[PLACEHOLDER]` fields in the context files (especially your profile/persona file if one was created).
> 2. Run the first skill on a real task to test it.
> 3. After a few uses, run `/kit-lessons` to apply what you've learned."

Do not close without confirming the user knows which skill to run first.
