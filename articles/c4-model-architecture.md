---
categories:
- documentation
created: '2026-07-18T06:09:37.592197+00:00'
id: c4-model-architecture
modified: '2026-07-18T06:09:37.592213+00:00'
tags:
- c4-model
- architecture
- diagrams
- documentation
title: The C4 Model for Software Architecture
type: leaf
---

The C4 model is a lean, hierarchical framework for visualizing software architecture. Rather than relying on unstructured, chaotic diagramming styles, C4 uses a "zoomable map" approach to break software architecture down into four strict levels of abstraction: **Context, Containers, Components, and Code**.

Because of its strict hierarchical and componentized nature, the C4 model is exceptionally well-suited for AI agents generating architectural documentation using tools like Mermaid.js.

### The Four Levels of Abstraction

1.  **Level 1: System Context**
    The highest level view. It shows the software system you are building and how it fits into the world around it (users, external systems, legacy databases). It completely ignores technical details like technologies or protocols.
    *   *AI Use Case*: Ideal for bounding the scope of the problem during the initial [[elicitation]] phase.
2.  **Level 2: Containers**
    Zooms into the System Context. A "Container" is any separately deployable unit (a web app, a mobile app, a database, a microservice). It shows the high-level technology choices and how the containers communicate.
    *   *AI Use Case*: Maps perfectly to [[bounded-contexts]] in Domain-Driven Design, showing how autonomous systems interact.
3.  **Level 3: Components**
    Zooms into an individual Container to show the internal components that make it up. These are the major building blocks or modules (e.g., "Authentication Controller", "Email Service").
    *   *AI Use Case*: Used by AIs to visualize the structural layout of a codebase before diving into the actual files.
4.  **Level 4: Code**
    Zooms into an individual Component to show how it is implemented (UML class diagrams, ER models). 
    *   *AI Use Case*: Rarely needed in modern documentation. AIs typically skip this level, as the actual source code (or [[source-code-plugin]] metadata) serves as the ultimate source of truth.

### Why C4 is Perfect for AI Agents

AIs struggle with generating massive, spaghetti-like "everything" diagrams. The C4 model forces AIs to generate small, highly scoped, and semantically dense diagrams using languages like Mermaid.

Instead of drawing the entire system, an AI can generate a localized Component diagram for a specific microservice. Because C4 standardizes the notation (boxes represent people/systems, lines represent relationships), AIs can reliably generate structurally sound visualizations that human engineers instantly understand.