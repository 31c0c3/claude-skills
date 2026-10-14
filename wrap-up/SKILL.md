---
name: wrap-up
description: Before closing a session: what it was about and what's left.
disable-model-invocation: true
---

# Wrap-up

I'm about to close this session and may not remember what it was about.
Closing loses the chat; files and commits stay.

1. Check every message of mine, from the first, for a **loose end**:
   something started, asked or promised and not finished:
   - a request not done or half done
   - a proposal or question waiting on my answer; an offer I never
     answered, such as `commit` or `distill`
   - a background task, agent or loop still running
   - our changes uncommitted: `git status --short` in each repo touched
   - a branch, worktree or temp file made for this session
   - a follow-up said only in chat
2. Reply in this shape:
   **Session:** one line: what it was about and what got done.
   **Left:** each loose end, costliest to lose first: what it is and the
   action that closes it. Omit it when there's none.
   **Bottom line:** the verdict alone, on its own line after a blank line,
   exactly one of:
   - `✓ Safe to close`
   - `✗ Not safe to close: <loose ends, a few words each>`

   Reasons and checks behind the verdict go in Session or Left.
3. On my yes, close them in order; a follow-up I defer goes to the repo's
   `TODO.md`. Then reply again in step 2's shape.
