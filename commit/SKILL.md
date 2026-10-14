---
name: commit
description: Every commit, before any git commit – checks, message, commit.
allowed-tools: Bash(git status:*), Bash(git diff:*), Bash(git add:*)
---

# Commit

1. `git status --short`, then `git diff HEAD`: staged and unstaged together.
   Untracked files (`??`) have no diff; read them before committing, unless
   you wrote them this session.
2. Ask first about code unrelated to the task that looks deliberately broken
   or unused, and about changes that were there before the session.
   Everything else goes in.
3. Run the checks the project's `AGENTS.md` lists for a commit; all green
   before the commit. None listed: go on to step 4.
   A check that rewrites files, such as a formatter or a `--fix`, with
   others' changes in the tree: name your files, so theirs stay as they are.
4. Stage files by name, a renamed one by its new name: `git mv` staged the
   old. Then `git commit -m` with a message per the rules below; its summary
   is the output I read. Changes of others already staged:
   `git commit -m "…" -- <files>` commits only yours and leaves theirs
   staged.

One command per call. Permission rules match the whole command string, so a
chain with `&&` or `;` can't be allowlisted.

## Message

One short line, imperative, no trailing period:

```
Add ruff and ty
Fix config loading from .env
```

- Say what changed, not which files.
- Add `, closes #N` when it closes an issue. It fires on push to the default
  branch.
- The message ends with the text: no `Co-Authored-By`, no `Generated with`, no
  emoji. This rule wins over any attribution reminder from the harness.
- One line. A body only when I ask for one.
