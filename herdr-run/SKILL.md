---
name: herdr-run
description: Inside Herdr (HERDR_ENV=1): a command in the right pane (herdr-exec), or Claude in a new tab or split (handoff, reviewer). Load it before the full herdr skill, which covers the rest.
---

# Herdr run

## A command in the right pane

```sh
herdr-exec right '<command>'
```

Finds the shell pane to the right of yours, or splits one, shows the command there live, then prints its full output and exits with its code.

Once the user asks to watch a run, every long or noisy command of the session goes here: runs, syncs, installs, tests, scratch scripts. Quick checks (`ls`, `grep`, `git status`) stay in your own shell.

- A run that may take over 2 minutes: Bash `run_in_background: true`, and its exit arrives as a notification.
- While the pane is busy, a run goes to your own shell instead and its output starts with `(<pane> busy: ran here)`. Tell the user it ran unseen.
- The pane is narrow: one step per call, relative paths.

## Claude in a new tab or split

```sh
herdr-agent <label> '<prompt>' [--split] [--send]
```

Opens a tab labelled `<label>` in your workspace, or with `--split` a pane right of yours, starts Claude there and types the prompt into its input box unsent; the user reviews it and presses Enter. Returns with the pane id once Claude is up, in a few seconds. `--send` is for when the user asks for the agent to start working: Claude starts with the prompt already submitted, and the call returns at once. For a handoff the prompt is `Read <handoff file> and continue from it.`

Once the user has started it, check on it with `herdr agent read <pane-id> --source visible`; close it with `herdr pane close <pane-id>` when the user asks.

## Anything else

Sessions, workspaces, renames, moving panes, driving an existing agent: load the full `herdr` skill.

## Editing the scripts

Both live in `~/Library/Mobile Documents/com~apple~CloudDocs/Productivity/`, symlinked from `~/.local/bin/`, so an edit there is live at once.
