---
name: herdr-handoff
description: Handoff to Claude in a new Herdr tab, the handoff file in its context. Use when asked to hand off work or move it to a new tab.
argument-hint: "What will the next session work on?"
---

Write a handoff to your scratchpad as `handoff-<topic>.md`: what a fresh agent needs to continue the work, focused on my arguments if any. Docs, commits and diffs go in by path, not copied.

Open it in a new tab, the file attached with `@`:

```sh
herdr-agent <topic> '@<file> Continue from this handoff.' --send
```
