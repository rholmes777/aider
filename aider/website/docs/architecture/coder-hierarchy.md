---
parent: Architecture
nav_order: 10
description: How Aider selects and uses different coder classes.
---

# Coder hierarchy

The `Coder` classes orchestrate all interactions with the LLMs. The base class in
[`aider/coders/base_coder.py`](https://github.com/Aider-AI/aider/blob/main/aider/coders/base_coder.py)
tracks chat history, manages repository context and applies edits returned by the model.
Specialized subclasses, declared in `aider/coders/__init__.py`, implement different
chat modes and edit formats.

`Coder.create()` picks the correct subclass by comparing the requested edit format
with each coder's `edit_format` attribute. When switching formats, it migrates
existing chat history and may summarize it to avoid confusing the new model.

Prompts are assembled via `ChatChunks`, grouping system messages, repo summaries,
file contents and conversation history. Some chunks are marked cacheable so providers
can reuse them across requests.
