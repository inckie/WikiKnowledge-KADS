---
categories: []
created: '2026-07-02T05:20:01.975266+00:00'
id: kads-root
modified: '2026-07-02T05:33:37.950323+00:00'
tags:
- ideology
- kads
- root
title: KADS Root Ideology
type: category
---

<!-- human:start -->
Welcome to the Knowledge Acquisition and Documentation Structuring (KADS) Ideology base. 

This knowledge base provides a foundational, systematic framework for transforming unstructured, tacit human expertise into explicit, verified, and machine-readable data assets. The core architectural principles are universally applicable to any complex, knowledge-intensive domain.

### The KADS Process Overview

Solving a knowledge engineering problem using KADS involves a strict, sequential pipeline:

1. **Elicitation**: Start by bounding the scope of the problem. Review existing artifacts to form a hypothesis, then engage Subject Matter Experts (SMEs) using structured interviews or protocol analysis. Extract their implicit mental models via bi-directional querying (discovery followed by validation) and formalize the logic flow.
2. **Structuring**: Take the chaotic raw data and classify it into three strict typologies: **Declarative** (facts and constraints), **Procedural** (step-by-step workflows), and **Structural** (architectural reasoning). Ensure your new taxonomy obeys mutual exclusivity and semantic consistency.
3. **Documentation**: Map the structured data into discrete, componentized documents rather than long narratives. Every piece of content must strictly be a **Concept**, a **Task**, or a **Reference**. Treat these documents as code (DaC), maintaining them in version control with peer reviews and linting.
4. **AI Integration**: Format your componentized documents with semantic Markdown headers, explicit YAML frontmatter, and hardcoded `[[wiki-links]]`. This ensures the knowledge graph is optimized for advanced AI retrieval systems, particularly GraphRAG, allowing AIs to traverse dependencies.
5. **Governance**: Assign granular ownership to every document. Implement programmatic deprecation policies and tie documentation audits to your engineering release cycles to prevent knowledge decay.

By following this pipeline, knowledge engineers (both human and AI) can capture domain expertise and construct a highly navigable, machine-readable knowledge graph.
<!-- human:end -->

<!-- ai:start -->
### [[elicitation|Elicitation Methodologies]]
Methodologies and protocols for actively extracting knowledge from subject matter experts, addressing the knowledge acquisition bottleneck.

### [[structuring|Structuring and Taxonomy]]
Guidelines for formalizing raw data into Declarative, Procedural, and Structural knowledge networks.

### [[documentation|Componentized Content Modeling]]
The framework for splitting dense documentation into single-purpose blocks using the Information Triad and treating Documentation as Code.

### [[ai-integration|AI Integration and RAG]]
Rules for optimizing componentized documentation for AI search and LLM context extraction using chunking paradigms.

### [[governance|Knowledge Governance]]
Policies for ensuring the knowledge base remains accurate, covering ownership, deprecation, and review lifecycles.

### [[software-engineering-case|Software Engineering Case Study]]
A case study on applying core KADS principles specifically to software architecture and development environments.

### [[ai-guides|AI Knowledge Engineering Guides]]
Actionable guides for AI agents to act autonomously as Knowledge Engineers in the KADS methodology.
<!-- ai:end -->