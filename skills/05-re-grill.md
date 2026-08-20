# Skill 05 — Re-Grill

**Invocation:** `/kit-re-grill`

**Purpose:** Targeted re-interview for a specific section of an actualized kit that needs rethinking — not patching. Use this when lessons-learned has revealed a structural problem, a new workflow has emerged, or the user's needs have shifted enough that the original grill no longer reflects reality.

The kit-builder stays the same. Only the actualized kit changes.

**Output:** A revised section of `kit-manifest.md` + revised files in the actualized kit.

---

## When to Use This vs. `/kit-lessons`

Use `/kit-lessons` when:
- A skill produced the wrong output shape
- A step was missing or in the wrong order
- A template needed a new field
- Claude made a bad assumption

Use `/kit-re-grill` when:
- A whole new workflow has emerged that wasn't in the original grill
- The user's role, domain, or context has changed significantly
- The kit's core persona or purpose no longer fits
- Multiple lessons-learned sessions have been patching the same underlying structural problem

If you're not sure which applies, ask:
> "Is this a patch or a rethink?"

---

## Before You Start

1. Ask which kit and where it lives.
2. Read `kit-manifest.md`, `AGENTS.md`, and `lessons-log.md` from that kit.
3. Ask:
   > "What area of the kit needs rethinking? Is it a specific workflow, the persona, the output format, or something else?"

Do not re-grill the whole kit unless the user explicitly asks. Target the area.

---

## Scoped Grill Protocol

Run a focused grill on only the area that needs rethinking. Use the relevant sections from `skills/01-grill.md` as your guide — but only the sections that apply.

For a new workflow: run Area 3 (Workflows) and Area 5 (Output Contract).
For a changed persona: run Area 1 (The Person) and Area 4 (The Context Problem).
For a new task: run Area 2 (Repeated Work) and Area 5 (Output Contract).
For a structural problem: run whichever areas the lessons-log points to.

Apply the same protocol: one question at a time, probe before moving on.

---

## Drafting the Revision

After the scoped grill, produce a revised section of the manifest:

> "Here's what I'd change in the manifest based on what we just covered. Read this before I touch any files."

Show only the sections that change. Wait for confirmation.

---

## Applying the Revision

Once the revised manifest section is approved:

1. Update `kit-manifest.md` with the new section.
2. Write or revise the affected skill files, templates, and AGENTS.md.
3. List every file changed.
4. Add an entry to `lessons-log.md` noting that a re-grill was run and what changed.

Say:
> "Re-grill applied. The kit-builder is unchanged. Your kit at [path] has been updated."
