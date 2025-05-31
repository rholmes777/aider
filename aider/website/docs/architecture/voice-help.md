---
parent: Architecture
nav_order: 50
description: Optional voice input and offline help search.
---

# Voice and help modules

The `/voice` command uses the `Voice` class from `aider/voice.py` to record audio
via `sounddevice`, encode it with `pydub` and transcribe through the active LLM.
This allows hands-free interaction with the coding session.

`aider/help.py` builds a local search index of the documentation using
`llama_index`. The `/help` command retrieves relevant pages and feeds them into
an assistant model so users can ask questions offline.
