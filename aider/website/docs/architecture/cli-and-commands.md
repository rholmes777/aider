---
parent: Architecture
nav_order: 20
description: Entry point, argument parsing and in-chat commands.
---

# CLI and commands

Program startup begins in `aider/main.py`. It parses command line arguments with
`ConfigArgParse` from `aider/args.py`, loads environment files and merges command
line settings with configuration from `.aider.conf`.

`main()` checks for a git repository, initializes models via `onboarding.select_default_model`
and constructs a `Coder` instance. Once running, user input is dispatched through
the `Commands` object defined in `aider/commands.py`. Commands such as `/commit`,
`/chat-mode` or `/voice` can modify coder state, switch chat modes or trigger
voice recording.

The CLI also supports optional browser and GUI front ends, plus clipboard and file
watchers that interrupt the prompt when new instructions are detected.
