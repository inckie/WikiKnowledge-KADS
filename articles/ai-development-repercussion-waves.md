---
categories:
- ai-guides
created: '2026-07-18T07:04:25.238280+00:00'
id: ai-development-repercussion-waves
modified: '2026-09-15T12:11:04.772859+00:00'
tags:
- ai-guides
- architecture
- specifications
- repercussion-waves
title: Specifications as Source of Truth & Repercussion Waves
type: leaf
---

# Specifications as Source of Truth & Repercussion Waves

In AI-driven development, the specification level (the Human Functional Requirements) serves as the ultimate, immutable source of truth.

## The Top-Down "Repercussion Wave"

Development operates strictly top-down. The specification layer "projects" downward into the architectural decomposition layer, which then projects downward into the actual code-level implementation.

When a human alters a top-level specification in the Knowledge Base, it triggers a **"Repercussion Wave"**:
1. **The Specification Changes**: A human updates the functional requirements (e.g., "The system must now support offline mode").
2. **Architectural Wave**: The AI agents detect this change and update the Architectural Overview layer in the KB (e.g., introducing an Event Sourcing multiplier to queue offline events).
3. **Code Level Wave**: Finally, the AI agents propagate this architectural change down into the codebase, rewriting the necessary modules and updating their embedded source code articles.

### Mandate for the Code Level Wave: Ponytail
When propagating specifications down into source code, AI agents **must strictly execute under [[ai-ponytail-strategy|AI Guide: Ponytail Minimalist Development Strategy]]**:
- Climb the ladder: reuse existing codebase utilities, leverage standard library functions, and avoid speculative scaffolding.
- The shortest working diff that satisfies the specification always wins.
- Ensure every non-trivial logic change leaves behind ONE runnable check (`assert` test or minimal test script).

## The Bottom-Up Isolation

Crucially, this wave only flows downward. 

If an AI or human refactors the code-level implementation—for instance, changing an internal algorithm to favor memory efficiency over raw speed—this change is **isolated**. As long as the external "contract" (the interface) remains the same, this bottom-up change does *not* trigger a reverse repercussion wave. The architectural overviews and the top-level specifications in the wiki remain completely untouched.

This isolation is why it is essential to keep implementation details strictly within the source code (as embedded short articles) rather than leaking them into the overarching WikiKnowledge graph. Ponytail's rules on deletion and minimal diffs ensure that code-level refactoring remains compact, safe, and contained.