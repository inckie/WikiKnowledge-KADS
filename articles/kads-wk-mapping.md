---
categories:
- ai-guides
created: '2026-07-02T05:42:16.455534+00:00'
id: kads-wk-mapping
modified: '2026-07-02T05:42:16.455559+00:00'
tags:
- mapping
- ai-guide
- wikiknowledge
- kads
title: Mapping KADS to WikiKnowledge
type: leaf
---

This guide explicitly maps the theoretical phases of the **KADS Methodology** directly to the technical features of **WikiKnowledge**. 

It serves as the definitive manual for AI Knowledge Engineers, demonstrating exactly *how* to execute KADS processes using the tools available in a WikiKnowledge base.

### 1. Elicitation
During the elicitation phase, the knowledge engineer bounds the scope of the problem and extracts tacit knowledge.

| KADS Concept | WikiKnowledge Feature | Implementation Strategy |
| :--- | :--- | :--- |
| **Scope Bounding & Hypothesis Design** | `<!-- human:start -->` blocks | The human architect uses the human-protected block in a category article to define the initial hypothesis and boundary. The AI must never overwrite this block. |
| **Trace Validation** | `<!-- ai:start -->` blocks | The AI synthesizes the verified traces and extracts summaries from the leaf articles, placing them exclusively in the AI-generated blocks. |

### 2. Structuring
Structuring requires organizing raw data into typologies while maintaining strict taxonomy rules like Mutual Exclusivity and Exhaustive Coverage.

| KADS Concept | WikiKnowledge Feature | Implementation Strategy |
| :--- | :--- | :--- |
| **Taxonomy Rules (Exhaustive Coverage)** | `categories` Frontmatter Array | Leaf articles declare their parent categories in the YAML frontmatter. This allows an article to participate in multiple structural trees without duplicating content. |
| **Knowledge Networks (Entity-Relation Mapping)** | Wiki Links (`[[article-id]]`) | AI agents draw formal edges between declarative facts and procedural workflows by embedding hardcoded double-bracket links directly within the Markdown body. |

### 3. Documentation
KADS mandates Componentized Content Modeling (The Information Triad) and Documentation-as-Code (DaC).

| KADS Concept | WikiKnowledge Feature | Implementation Strategy |
| :--- | :--- | :--- |
| **Componentized Modeling (The Triad)** | `type: leaf` Articles | Every leaf article must strictly adhere to one purpose (Concept, Task, or Reference). AI agents must refuse to author sprawling, multi-purpose narrative wikis. |
| **Documentation-as-Code (DaC)** | Markdown Files | All knowledge is stored as plain-text `.md` files, ensuring compatibility with IDEs, version control systems, and static site generators. |

### 4. AI Integration (RAG)
To make knowledge machine-readable for advanced LLM search architectures (like GraphRAG), the documentation must be structurally sound.

| KADS Concept | WikiKnowledge Feature | Implementation Strategy |
| :--- | :--- | :--- |
| **Semantic Chunking & Context** | YAML Frontmatter | The frontmatter injects structured, machine-readable metadata (`id`, `tags`, `categories`, `modified`) at the top of every file, instantly anchoring the LLM's context window. |
| **Explicit Relationship Topologies** | Backlinks | The system automatically extracts forward Wiki Links and computes reverse backlinks, allowing GraphRAG agents to execute multi-hop graph traversal algorithms seamlessly. |

### 5. Governance
Without governance, knowledge decays. The system must enforce continuous review lifecycles.

| KADS Concept | WikiKnowledge Feature | Implementation Strategy |
| :--- | :--- | :--- |
| **Automated Review Triggers** | "Dirty" Category Status | When a leaf article is updated, its parent category's `modified` timestamp falls behind. AI agents use `get_category_status()` to flag these "dirty" categories and autonomously rewrite the `<!-- ai:start -->` summary blocks to maintain synchronization. |
| **Preventing Knowledge Loss** | Unmentioned Highlighting | The WikiKnowledge UI automatically highlights leaf articles that belong to a category but are missing from its summary block, ensuring absolute Exhaustive Coverage. |