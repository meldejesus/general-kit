# Kit Builder

A meta-kit that builds kits. You describe what you do; it builds a Claude Code workflow kit tailored to you.

The kit-builder itself never changes. The kit it produces is yours to evolve.

---

## How It Works

```
Grill → Draft → Actualize → Use → Lessons → Revise
```

### Phase 1 — Grill
Claude interviews you about your domain, your repeated work, your pain points, and what good output looks like. One question at a time. No forms.

Run: `/kit-grill`

Output: `grill-output.md` in your working directory.

### Phase 2 — Draft
Claude reads the grill output and produces a `kit-manifest.md` — the full spec of the kit before any files are written. You review it and push back.

Run: `/kit-draft`

Output: `kit-manifest.md`

### Phase 3 — Actualize
Claude reads the manifest and writes the kit: `AGENTS.md`, `README.md`, all skill files, all templates. The kit lands in a directory you name.

Run: `/kit-actualize`

Output: your new kit directory, ready to use.

### Phase 4 — Lessons Learned
After real use, you describe what broke, what was awkward, or what you learned. Claude applies it to the actualized kit — revising skills, templates, and AGENTS.md — without touching the kit-builder.

Run: `/kit-lessons`

### Phase 5 — Re-Grill (optional)
When the kit has drifted far enough from what you need, run a focused re-grill on a specific area (a new workflow, a changed persona, a new output type). Produces a revised manifest section, then feeds back into actualize for that section only.

Run: `/kit-re-grill`

---

## Key Files

| File | Purpose |
|---|---|
| `skills/01-grill.md` | The grilling session — interviews you before building anything |
| `skills/02-draft-kit.md` | Builds the kit manifest from grill output |
| `skills/03-actualize.md` | Writes the actual kit files from the manifest |
| `skills/04-lessons-learned.md` | Applies real-world learnings to revise the actualized kit |
| `skills/05-re-grill.md` | Targeted re-interview when a section of the kit needs rethinking |
| `templates/grill-output.md` | Structure the grill session writes into |
| `templates/kit-manifest.md` | Full kit spec template |
| `templates/lessons-log.md` | Running lessons log that lives inside the actualized kit |
| `docs/kit-anatomy.md` | What every good kit needs and why |

---

## What This Produces

A kit has:
- `AGENTS.md` — who Claude is in this kit, what context it has upfront, what it never does
- `README.md` — how a human uses the kit
- `skills/` — one skill file per discrete task or workflow
- `templates/` — fillable artifacts the kit produces
- `docs/` — reference material Claude needs to do good work
- `lessons-log.md` — the running record of what's been learned in the field

The kit-builder produces all of these. You run it, use the kit, then improve the kit over time through `/kit-lessons`. The kit-builder itself stays stable.
