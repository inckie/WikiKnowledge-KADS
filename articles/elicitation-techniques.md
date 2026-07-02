---
categories:
- elicitation
created: '2026-07-02T05:26:18.948054+00:00'
id: elicitation-techniques
modified: '2026-07-02T05:26:18.948070+00:00'
tags:
- techniques
- interviews
- protocol-analysis
title: Elicitation Techniques
type: leaf
---

To extract varied layers of human expertise, a knowledge engineer must deploy a diverse suite of elicitation methodologies, matching the technique to the target cognitive behavior.

* **Engineered Structured Interviews**: Passive interviewing yields narrative-heavy, disjointed data. KADS mandates the use of pre-constructed, goal-oriented question matrices. These matrices isolate specific architectural boundaries, systemic failure modes, and critical decision trees. The interviewer guides the expert through a pre-mapped algorithmic progression, systematically checking inputs, constraints, and outputs at every node.
* **Cognitive Protocol Analysis**: This technique captures "in-flight" cognitive processing. The knowledge engineer observes a subject matter expert (SME) during an active, real-world problem-solving session. The expert is instructed to verbalize their entire thought process concurrently ("think-aloud protocol"). The engineer records this stream of consciousness, tracking the expert's focus, the subtle cues they prioritize, and the immediate hypotheses they form or discard. This uncovers the undocumented "tribal knowledge" and heuristic shortcuts that rarely surface in standard manuals.
* **Multi-Artifact Ingestion and Archaeology**: Human memory is fallible and prone to recency bias. Before engaging an expert directly, the knowledge engineer must conduct data archeology on all available technical artifacts (manuals, legacy architectural designs, system configurations, telemetry dashboards, logs). This creates a factual baseline of the domain, allowing the engineer to enter interviews with a foundational framework, optimizing valuable time with the expert.