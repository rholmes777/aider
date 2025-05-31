---
parent: Architecture
nav_order: 70
description: Handling large replies with assistant prefill.
---

# Infinite output

Some models support an assistant prefill parameter that lets Aider continue
responses across multiple requests. When a reply reaches the model's output limit,
Aider sends the partial text back to the model as a prefix so generation can
resume seamlessly. This enables effectively unlimited output sizes.

See [Infinite output](../more/infinite-output.html) for the list of models that
support this feature.
