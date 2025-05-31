---
parent: Architecture
nav_order: 60
description: Watching for AI comments in your editor.
---

# File watching

Running Aider with `--watch-files` activates the `FileWatcher` from
`aider/watch.py`. It monitors your working tree for comments ending with `AI!` or
`AI?`. When such markers are detected, the watcher interrupts the CLI prompt and
collects all matching comments, sending them to the model as instructions or
questions.

This feature makes it easy to use Aider directly from an IDE: simply type AI
comments in your code, save the file and let the watcher handle the rest.
