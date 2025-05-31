---
parent: Architecture
nav_order: 40
description: How Aider stages, commits and attributes code changes.
---

# Git workflow

`GitRepo` in `aider/repo.py` wraps GitPython to handle version control. The
`commit()` method generates commit messages, applies attribution flags and creates
commits using the selected model. When auto commit is enabled, `Coder.auto_commit()`
runs after each batch of edits and reports the resulting hash back to the chat.

The repo map, linter and test hooks all rely on Git to determine which files have
changed. If errors occur, users can fall back to standard Git commands to inspect
or revert modifications.
