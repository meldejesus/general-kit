# Kit Builder — Quick Start

## What's Here

**The engine (never changes):**

| Skill | Invocation | What it does |
|---|---|---|
| `skills/01-grill.md` | `/kit-grill` | One-question-at-a-time interview across 6 areas: person, repeated tasks, workflows, context problem, output contract, lessons so far |
| `skills/02-draft-kit.md` | `/kit-draft` | Builds the kit manifest section by section with confirmation at each step before locking it |
| `skills/03-actualize.md` | `/kit-actualize` | Writes all kit files from the approved manifest in strict order |
| `skills/04-lessons-learned.md` | `/kit-lessons` | Classifies learnings by type (wrong output shape, missing context, new task, etc.) and routes the fix to the right file |
| `skills/05-re-grill.md` | `/kit-re-grill` | Scoped re-interview when patching isn't enough and structure needs rethinking |

## The Key Separation

The kit-builder is read-only once deployed. Everything `/kit-lessons` and `/kit-re-grill` touch lives inside the actualized kit — never the kit-builder itself.

## To Build Your First Kit

Open a session in this directory and run:

```
/kit-grill
```

It will ask one question at a time. When the grill is done, run `/kit-draft` to build the manifest, review and approve it, then run `/kit-actualize` to write the kit.

## After Real-World Use

Run `/kit-lessons` to apply what you've learned. It classifies each lesson and makes targeted changes to the right files. For deeper structural rethinking, run `/kit-re-grill` on the area that needs it.
