---
categories:
- ai-guides
created: '2026-07-18T07:04:23.159236+00:00'
id: ai-source-code-strategy
modified: '2026-07-18T07:04:23.159270+00:00'
tags:
- ai-guides
- source-code
- strategy
- metadata
title: 'AI Guide: Source Code Knowledge Strategy'
type: leaf
---

# AI Guide: Source Code Knowledge Strategy

When code is heavily written by AIs, humans act as the specifiers of functional requirements. AIs must strictly maintain the separation between high-level architecture in the wiki and low-level implementations in the source code.

## The Rule of Non-Duplication

**Do not transcribe raw code implementations (classes, interfaces, endpoints) into the knowledge base wiki.**

If you duplicate detailed REST APIs or internal class structures into a wiki article, you create a massive synchronization nightmare. When the code changes, the wiki instantly rots. 

## Embedding Short Articles in Code

Instead of writing implementation details in the wiki, you must write **short articles directly inside the source code files** using docstrings (similar to JavaDoc or JSDoc). 

These embedded articles act as the definitive documentation for the "Implementation Layer". By using the `source-code-plugin`, these docstrings are automatically imported into the knowledge graph as virtual articles.

### Why is this critical for AIs?
1. **Context Proximity**: The documentation lives immediately next to the code it describes. When humans or AIs read the file, they instantly understand the intent without having to search the wiki.
2. **Token Efficiency**: AIs do not need to burn tens of thousands of tokens trying to "recover" knowledge by parsing raw function bodies, ASTs, or massive codebases. They can simply read the short article you wrote at the top of the file to grasp the exact purpose and interfaces of the module.
3. **Encapsulated Refactoring**: The code-level implementation can be completely rewritten (e.g., swapping an array for a hash map to favor speed) without changing the external "contract" or requiring any updates to the top-level wiki architecture.