---
categories:
- software-design-multipliers
created: '2026-07-18T05:16:52.313574+00:00'
id: ecs-multiplier
modified: '2026-07-18T05:16:52.313589+00:00'
tags:
- ecs
- data-oriented-design
- multiplier
- architecture
title: Entity Component Systems (ECS) / Data-Oriented Design
type: leaf
---

Commonly used in game engines, ECS completely abandons Object-Oriented inheritance. An "Entity" is just an integer ID. A "Component" is a plain struct of data (no logic). A "System" is a function that iterates over arrays of specific components.

### What this one idea unlocks:

*   **Extreme CPU Cache Locality:** Because data is packed into contiguous arrays by type (rather than scattered across the heap inside object instances), iterating over thousands of items becomes exponentially faster.
*   **Dynamic Composition at Runtime:** Designers can create entirely new object types while the program is running simply by attaching new component IDs to an entity ID. No class hierarchies to recompile.
*   **Effortless Multi-threading:** Because systems separate data and logic, you know exactly which systems read and write which components. If two systems touch different component arrays, they can be run in parallel automatically with zero locks.
*   **Trivial Serialization / Save States:** Saving the game state just means dumping raw arrays of structs directly to disk.