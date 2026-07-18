---
categories:
- software-design-multipliers
created: '2026-07-18T05:16:56.467501+00:00'
id: coroutines-multiplier
modified: '2026-07-18T05:16:56.467516+00:00'
tags:
- coroutines
- continuations
- multiplier
- architecture
title: Execution State as Data (Coroutines / Continuations)
type: leaf
---

Instead of a function executing from start to finish on the stack, the language/runtime allows you to pause a function, pack its current local variables and execution pointer into an object (a continuation), and return control to the main loop.

### What this one idea unlocks:

*   **Flattening Asynchronous Code:** It eliminates "callback hell." You can write code that looks like a normal, blocking procedural script, but it yields perfectly to the event loop while waiting for network/disk I/O.
*   **Procedural State Machines:** Instead of writing complex switch/case state machines for character AI or dialogue trees, you can just write a single linear function with yield statements that pause execution until the next frame or event.
*   **Generators / Lazy Evaluation:** You can build infinite lists or streams where the next item is only computed exactly when the caller requests it.