---
parent: Architecture
nav_order: 30
description: Managing token budgets and summarizing chat history.
---

# Memory and context

Each model defines `max_chat_history_tokens`, roughly 1/16 of its context window.
When the conversation exceeds this budget, a background summarizer thread in
`ChatSummary` compacts older messages into a short summary.

On startup, Aider can restore previous conversations from `chat_history.md` if
`--restore-chat-history` is enabled. This keeps long-running tasks focused across
sessions while controlling token cost.

The `Coder` tracks total tokens sent and received. If the LLM returns a
`FinishReasonLength` error, Aider warns the user and may resume generation using
models that support assistant prefill ("infinite output").
