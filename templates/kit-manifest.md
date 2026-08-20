# Kit Manifest

<!-- Written by /kit-draft. Approved before /kit-actualize runs. -->

**Date:** [DATE]
**Kit name:** [KIT-NAME]
**Target directory:** [FULL PATH]
**Grill output:** `grill-output.md` (date: [DATE])

---

## 1. Purpose

**One sentence:** [What this kit does]

**For whom:** [User persona — who is this kit for]

**What it is not:** [Scope boundaries — what this kit explicitly does not handle]

---

## 2. User Persona

<!-- Claude reads this at the start of every session in the actualized kit -->

[3-5 sentences describing who the user is, what they already know, their preferences, and their deal-breakers. Written in second person as if Claude is being briefed: "The user is a...", "They already know...", "They do not want..."]

---

## 3. Task Inventory

| # | Task Name | Input | Output | Destination | Skill File |
|---|---|---|---|---|---|
| 1 | [name] | [input] | [output] | [destination] | `skills/01-[slug].md` |
| 2 | [name] | [input] | [output] | [destination] | `skills/02-[slug].md` |

---

## 4. Workflow Maps

### Workflow: [NAME]

**Trigger:** [What starts this workflow]

```
Step 1: [action] → Output: [Y]
Step 2: [decision]
  → If [A]: Step 3
  → If [B]: Step 5
Step 3: [action] → Output: [Y]
...
Final: [what the workflow produces end to end]
```

**Failure modes:** [Where this typically breaks]
**Handoffs:** [Where work leaves Claude]

<!-- Add more workflows as needed -->

---

## 5. Context Files

| File | Contents | Created by | Loaded by |
|---|---|---|---|
| [filename] | [what's in it] | [user / Claude / existing] | [which skills] |

---

## 6. Template Inventory

| Template | Produced by | Used by |
|---|---|---|
| `templates/[name].md` | `skills/[NN]-[slug].md` | [user / next skill / external] |

---

## 7. Directory Layout

```
[kit-name]/
  AGENTS.md
  README.md
  lessons-log.md
  skills/
    01-[slug].md
    02-[slug].md
  templates/
    [name].md
  docs/
    [name].md
  [context-files]/
    [filename]
```

---

## 8. AGENTS.md Outline

**Persona Claude adopts:** [description]
**Hard constraints (never do):**
- [constraint]
- [constraint]

**Skills index:**
| Invocation | File | What it does |
|---|---|---|
| `/[cmd]` | `skills/NN-[slug].md` | [one line] |

**Context files to read at session start:**
- `[file]` — [why]

---

## 9. Lessons Seed

[Lessons from the grill to pre-load into lessons-log.md]

- [lesson]
- [lesson]

*None yet.*

---

## Approval

- [ ] Task inventory is correct and complete
- [ ] Workflow maps match how this actually works
- [ ] Context files cover what Claude needs
- [ ] Output contracts are defined for each task
- [ ] Directory layout makes sense

**Approved by:** [user] on [DATE]
