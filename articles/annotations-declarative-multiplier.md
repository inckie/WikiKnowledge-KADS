---
categories:
- software-design-multipliers
created: '2026-07-18T05:38:17.204535+00:00'
id: annotations-declarative-multiplier
modified: '2026-07-18T05:38:17.204553+00:00'
tags:
- annotations
- attributes
- declarative
- multiplier
- architecture
title: Annotations / Attributes (Declarative Programming)
type: leaf
---

Instead of writing imperative setup code to register API routes, map JSON fields, or enforce validation rules, you attach metadata directly to your classes and methods using Annotations (Kotlin/Java) or Attributes (C#).

### What this one idea unlocks:

*   **Framework Magic & Auto-Wiring:** At application startup, the framework uses reflection to scan the codebase for these markers. By simply placing `[HttpGet("/users")]` on a method, the framework auto-wires the HTTP routing, handles JSON serialization, and generates a complete OpenAPI/Swagger documentation page automatically.
*   **AOP Integration:** It ties perfectly into Dynamic Proxies. You can invent your own annotations like `[RequiresAdmin]` or `[RetryOnFailure]`. A proxy will intercept calls and automatically enforce that logic based purely on the presence of the metadata, keeping business logic entirely decoupled from infrastructure concerns.