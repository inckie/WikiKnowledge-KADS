---
categories:
- documentation
created: '2026-07-02T05:20:42.940816+00:00'
id: information-triad
modified: '2026-07-02T05:20:42.940834+00:00'
tags:
- triad
- dita
- concept
- task
- reference
title: The Information Triad
type: leaf
---

Every piece of technical documentation must be strictly isolated into one of three structural formats, known as the Information Triad (inspired by DITA architecture):

| Component Type | Core Objective | Structural Constraints & Requirements |
|---|---|---|
| **Concept** | Explains background, architectural theory, and conceptual foundations. | Must contain only high-level definitions, architectural diagrams, and abstract principles. Strictly zero step-by-step instructions or copy-pasteable commands. |
| **Task** | Guides a user through a specific, repeatable technical procedure. | Must use a strict ordered list (1., 2., 3.). Must state prerequisites before step one, and explicitly define the expected outcome after the final step. |
| **Reference** | Provides immediate, non-narrative lookup data for active work. | Must be structured using scannable tables, exact API schemas, exhaustive error code lists, configuration keys, or command-line flag definitions. |