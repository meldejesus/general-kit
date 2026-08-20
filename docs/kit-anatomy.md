# Kit Anatomy

Every kit built by kit-builder follows this structure. Understanding why each part exists helps you build kits that actually get used.

---

## The Seven Parts

### 1. AGENTS.md

The most important file. Claude reads it at the start of every session.

A good AGENTS.md contains:
- **A persona** — who Claude is in this kit. Not generic. Specific to the domain.
- **A user profile** — who the user is, what they know, their deal-breakers. Claude should never have to guess this.
- **The skill index** — every invocation command with a one-line description. Claude's map of what it can do.
- **Context loading instructions** — which files to read at the start of each session, and why.
- **Hard constraints** — things Claude must never do in this kit. Explicit. Non-negotiable.
- **Output quality bar** — what good work looks like in this domain.

An AGENTS.md that could apply to any kit is a failed AGENTS.md.

### 2. README.md

Human-facing. Short. Covers:
- What the kit does (2-3 sentences)
- The workflow sequence and what each step produces
- Key files table
- Quick start steps

The README is for the person, not for Claude.

### 3. Skills

One skill file per discrete task or workflow. Named `NN-slug.md` to control load order.

A good skill file contains:
- **Invocation** — the slash command
- **Purpose** — one sentence
- **Input** — what the skill expects before it starts
- **Steps** — numbered, concrete, with decision points explicitly called out
- **Output** — exactly what gets written or returned, in what format, where it goes
- **What comes next** — which skill to run after this one

A skill file that says "analyze X" without saying how to analyze it, what to look for, and what to do when something is ambiguous has not been written.

### 4. Templates

Fillable artifacts the kit produces. Named by what they represent, not by which skill writes them.

A good template:
- Uses `[PLACEHOLDER]` for every field that gets filled in
- Has consistent headers that other skills can navigate by name
- Includes a comment at the top explaining what it is and which skill produces it
- Is the same format every time — templates exist because consistency matters

### 5. Docs

Reference material Claude needs that isn't a template and isn't a skill. Examples:
- Domain terminology and rules
- Decision rubrics (how to score, rank, or evaluate something)
- Authority hierarchies (which source wins when sources conflict)
- Edge case catalogs

Docs are reference, not instructions. Skills are instructions.

### 6. Context Files

Files about the specific user, project, or environment that Claude needs to do good work. Examples:
- A personal profile (`profile.md`, `specifics.md`)
- A list of companies, people, or constraints
- A style guide or tone guide
- A running tracker or log

Context files are filled in by the user (or generated once and then maintained). They are not templates — they're live reference data.

### 7. Lessons Log

The mechanism for the kit to evolve. `lessons-log.md` lives inside the actualized kit.

A good lessons log:
- Records what was learned and what changed, not just what went wrong
- Is updated by `/kit-lessons` after real use
- Captures open questions and unresolved edge cases
- Provides the input for `/kit-re-grill` when structural rethinking is needed

The lessons log is how a kit stays useful over time instead of going stale.

---

## What a Kit Is Not

- A collection of prompts. Prompts go in a notes file. Kits are workflow systems.
- Documentation for a human to read and manually follow. Everything a human has to manually do is a gap.
- A one-time thing. A kit that can't evolve will be abandoned.
- A generic tool. A kit that could work for anyone will work well for no one.

---

## Signs a Kit Is Working

- The user runs it without referring to the README
- The output is consistent enough that a change is obvious
- The lessons log has entries
- The skill files have been revised at least once

## Signs a Kit Needs Rethinking

- The user keeps having to add context that should already be in AGENTS.md
- The same lesson keeps appearing in the log
- A workflow is getting used differently than it was designed
- New tasks have appeared that aren't in any skill file
