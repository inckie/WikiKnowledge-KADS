---
categories:
- domain-driven-design
created: '2026-07-02T06:13:33.900434+00:00'
id: domain-specific-modeling
modified: '2026-07-18T06:02:23.941395+00:00'
tags:
- dsm
- reflection
- scripting
- serialization
title: Domain-Specific Modeling (DSM)
type: leaf
---

Domain-Specific Modeling (DSM) is the practice of creating flexible, generic building blocks at the foundation layer that can be dynamically assembled to reflect the top-level ubiquitous language.

Rather than hardcoding rigid classes for every possible domain variation, DSM relies on highly generalized software architectures. This generalization allows the system to instantly adapt to new requirements without massive refactoring, effectively ensuring the software model mirrors the business domain dynamically.

### Implementing DSM via Multipliers
To achieve this level of flexibility, DSM relies heavily on implementing specific [[software-design-multipliers]]:

* **[[reflection-multiplier|Reflection and Unification]]**: Instead of writing boilerplate, the system relies on retaining architectural metadata. This unlocks automatic serialization, network transport, and the ability to instantly adapt to new schemas.
* **[[dynamic-proxies-multiplier|Scripting Bindings & Proxies]]**: By exposing these foundational objects through transparent proxies or bindings, top-level domain logic can be written dynamically by technical designers using scripting languages (like Lua or JS). The system is modeled to adapt to the domain, rather than forcing the domain to adapt to the system's rigid constraints.
* **[[ecs-multiplier|Dynamic Composition]]**: Often paired with Data-Oriented Design, generalized entities can be composed entirely at runtime, allowing specific implementations to be swapped out without breaking the domain model.