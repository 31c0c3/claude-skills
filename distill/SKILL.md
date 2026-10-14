---
name: distill
description: Distill the session's lessons into the repo. Offer it when the work is done; run it on yes.
allowed-tools: Bash(git log:*), Bash(git status:*), Bash(git diff:*), Bash(gh issue list:*)
---

# Distill

A **lesson** is what the next session can't work out for itself. The rest is
already kept: in the code, the diff, git history, `--help`, the project's
plans.

1. List for yourself every candidate lesson, one line each: each correction
   I made, each retry, each why that took a detour. `git status --short`
   adds unfinished work. Done when the list covers the session from its
   first message.
2. Give each one a home. A home the project's `AGENTS.md` names, such as a
   notes file or GitHub issues, replaces the default below:
   - a rule every session needs → `AGENTS.md`
   - steps for one kind of task → that task's skill, new or existing
   - a why or a gotcha → a comment or docstring beside the code it explains
   - a command → `README.md`
   - unfinished work → `TODO.md`
   - already kept, obvious in hindsight, or what the model does by default →
     drop. Drop is the default.
3. Hunt the **sediment**: lines this session made stale, such as a fixed bug,
   a renamed file or a plan now done. Fix or delete them; one corrected line
   beats three new ones. Done when every file this session changed, and
   each doc that names one, is checked.
4. Propose only what's **to add** or **to fix** (sediment), most valuable
   first: likeliest to recur, costliest when it does. Each in plain words,
   readable without the diff: the idea and its home in bold, why it's worth
   it in a line, then the exact text. One closing line counts the rest,
   already kept or dropped; list them only on ask. On yes, write them, run
   `commit`, and show what's left to add or fix.
