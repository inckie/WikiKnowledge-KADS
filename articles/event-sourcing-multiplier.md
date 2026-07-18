---
categories:
- software-design-multipliers
created: '2026-07-18T05:16:50.232163+00:00'
id: event-sourcing-multiplier
modified: '2026-07-18T05:16:50.232180+00:00'
tags:
- event-sourcing
- multiplier
- architecture
title: The Append-Only Log (Event Sourcing)
type: leaf
---

Instead of updating the current state of an object (e.g., changing a user's balance from $50 to $100), you store the events that caused the change (e.g., Deposited($50)). The current state is just a projection calculated by folding all historical events together.

### What this one idea unlocks:

*   **Time-Travel Debugging:** You can reconstruct the exact state of the application at any millisecond in the past to see exactly how a bug occurred.
*   **Trivial Undo/Redo:** Moving backward and forward in state is just a matter of removing or re-applying the latest events.
*   **Crash Recovery & Replication:** If a server dies, another server can perfectly rebuild the state just by reading the event log. You can also broadcast these events to sync clients over a network smoothly.
*   **Audit Trails:** Security and auditing come for free, because the system inherently records the "who, what, and when" of every state mutation.