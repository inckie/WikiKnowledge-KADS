---
categories:
- ai-guides
created: '2026-07-02T07:06:25.956529+00:00'
id: ddd-wk-mapping
modified: '2026-07-02T07:06:25.956550+00:00'
tags:
- mapping
- ddd
- wikiknowledge
- ai-guide
title: Mapping DDD to WikiKnowledge
type: leaf
---

This guide explicitly maps the structural patterns of **Domain-Driven Design (DDD)** directly to the technical features of **WikiKnowledge**.

It serves as a manual for AI Knowledge Engineers to build scalable, domain-driven knowledge graphs without breaking architectural boundaries.

### 1. Ubiquitous Language
A shared, strict vocabulary between experts, codebases, and AIs.

| DDD Concept | WikiKnowledge Feature | Implementation Strategy |
| :--- | :--- | :--- |
| **Domain Nouns & Adjectives** | `title` and `tags` Frontmatter | Domain entities and their explicit states (e.g., `CancelledOrder`) must precisely match the file's `title`. The exact noun must also be embedded in the `tags` array to enforce semantic search consistency. |
| **Eliminating Translation Layers** | Wiki Links (`[[article-id]]`) | Instead of describing a domain concept with loose narrative text, AI agents must hard-link the exact noun using `[[id]]` syntax. This forces the entire knowledge graph to coalesce around a single source of truth for that term. |

### 2. Bounded Contexts
Strict architectural boundaries isolating specific ubiquitous languages.

| DDD Concept | WikiKnowledge Feature | Implementation Strategy |
| :--- | :--- | :--- |
| **Context Boundaries** | `type: category` Articles | Each major category acts as a Bounded Context (e.g., `sales-domain`, `shipping-domain`). The human architect uses the `<!-- human:start -->` block to define the explicit linguistic rules and borders of that specific context. |
| **Semantic Isolation** | `categories` Frontmatter Array | Leaf articles bind themselves to a specific context by declaring the category ID in their frontmatter. A leaf should generally only belong to one primary domain context to avoid polluting semantics across boundaries. |

### 3. Anti-Corruption Layers & Event Buses
How isolated contexts safely communicate without polluting each other's internal models.

| DDD Concept | WikiKnowledge Feature | Implementation Strategy |
| :--- | :--- | :--- |
| **Cross-Context Mapping (Event Bus)** | Backlink Traversal | When distinct bounded contexts need to interact, they map to each other via links. The GraphRAG system uses computed backlinks to build a topographical "Event Bus," mapping exactly how a change in a Core Domain ripples to an upstream/downstream Support Domain. |

### 4. Domain-Specific Modeling
Building generalized foundation blocks that dynamically adapt to the top-level domain logic.

| DDD Concept | WikiKnowledge Feature | Implementation Strategy |
| :--- | :--- | :--- |
| **Reflection & Unification** | The `Article` Data Model | The WikiKnowledge `markdown_backend.py` abstracts every domain concept into a unified `Article` python object. It relies on generalized attributes (ID, Title, Tags, Content) rather than forcing developers to write rigid, hardcoded classes for every new domain entity. |
| **Dynamic Serialization** | YAML Frontmatter + Markdown | Complex domain knowledge is serialized into a universal, machine-readable format. This ensures that the domain logic can be instantly parsed, edited, or exposed to external scripting engines (like Lua/JS bindings) without any translation boilerplate. |