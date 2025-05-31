---
parent: Architecture
nav_order: 90
description: Recovering from interruptions and tracking token cost.
---

# Session resumption and cost tracking

Aider keeps running totals of tokens sent and received in each session. These
are displayed when the program exits. Models that report pricing allow Aider to
estimate cost based on token usage.

If `Control-C` is pressed while waiting for a model reply, the current request is
cancelled and the prompt returns, preserving any pending edits. Previous chats can
be restored on startup, ensuring continuity even after a restart or crash.
