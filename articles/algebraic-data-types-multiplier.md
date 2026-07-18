---
categories:
- software-design-multipliers
created: '2026-07-18T05:21:37.054839+00:00'
id: algebraic-data-types-multiplier
modified: '2026-07-18T05:21:37.054855+00:00'
tags:
- adt
- type-systems
- multiplier
- architecture
title: Algebraic Data Types (Sum and Product Types)
type: leaf
---

Instead of modeling data using generic primitives (strings, ints, nulls) or standard OOP class inheritance, you use strict combinations of "AND" (Product types, like Structs) and "OR" (Sum types, like Enums that carry data payloads).

### What this one idea unlocks:

*   **"Make Illegal States Unrepresentable":** You can structure your data so that invalid configurations literally will not compile. You eliminate the need for hundreds of runtime `if (isValid)` checks because the compiler guarantees the data is valid by definition.
*   **Exhaustiveness Checking:** The compiler acts as an assistant. If you add a new state to a system (e.g., adding `Refunded` to a `PaymentStatus` enum), the compiler will immediately flag every single `switch` statement in your entire codebase where you forgot to handle the new state.
*   **Free Property-Based Testing:** Because the types are mathematically sound, testing frameworks can automatically generate thousands of randomized, valid test cases based purely on the type signatures without you writing a single mock object.