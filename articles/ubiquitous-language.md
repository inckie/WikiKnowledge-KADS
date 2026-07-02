---
categories:
- domain-driven-design
created: '2026-07-02T06:13:29.733928+00:00'
id: ubiquitous-language
modified: '2026-07-02T06:15:25.580949+00:00'
tags:
- ubiquitous-language
- vocabulary
- semantics
title: Ubiquitous Language
type: leaf
---

A Ubiquitous Language is a shared, strictly defined vocabulary used equally by domain experts, software engineers, and AI agents. It is the practical software application of the KADS "Semantic Consistency" rule.

* **Nouns (Entities & Values)**: Every concept elicited from an expert must be given a strict, unambiguous noun. If the business calls it an `Order`, the codebase must have a `class Order`, the database must have an `orders` table, and the AI prompt must refer to an `Order`. Synonyms (like `Purchase` or `Transaction`) are strictly banned within the same bounded context.
* **Verbs (Commands & Events)**: Procedures and state transitions must be mapped to specific verbs. If a user cancels an order, the ubiquitous language dictates the verb is `CancelOrder`. The top-level application logic should read like English, directly implementing these nouns and verbs (e.g., `Order.Cancel()`), while delegating the complex execution down to the infrastructure layer. 
* **Adjectives (States & Conditions)**: When a noun undergoes a state transition, the resulting state must be explicitly defined as an adjective. Instead of relying on ambiguous boolean flags (like `is_cancelled = true`), the ubiquitous language models these states explicitly (e.g., `CancelledOrder` or `PendingOrder`). This forces the top-level logic to treat different states of an entity as distinct semantic concepts with their own unique behaviors and validation rules.
* **Shared Communication**: By forcing humans, codebases, and AIs to use this exact vocabulary, you eliminate the translation layer that typically causes systemic bugs and knowledge fragmentation.