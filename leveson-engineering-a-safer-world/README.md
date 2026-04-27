# Engineering a Safer World

- **Full title:** Engineering a Safer World: Systems Thinking Applied to Safety
- **Author:** Nancy G. Leveson
- **Published by:** MIT Press
- **Date:** 2011
- **Source:** https://mitpress.mit.edu/9780262533690/engineering-a-safer-world/

## About

A foundational text on systems-theoretic safety engineering. Leveson argues that traditional approaches to safety (fault trees, event chains, component reliability) fail for modern sociotechnical systems — software-intensive, organizationally complex systems where accidents emerge from interactions rather than component failures. She introduces STAMP (Systems-Theoretic Accident Model and Processes) and STPA (System-Theoretic Process Analysis), a hazard analysis technique that treats safety as a control problem rather than a failure-prevention problem.

Core thesis: safety is an emergent property of the whole system, not a property of individual components. A perfectly reliable component executing an unsafe design produces reliable unsafety. Accidents result from inadequate control structures — specifically, when the controller's model of the process diverges from reality and the feedback channels that would correct the divergence are absent, broken, or filtered out.

## Note on this entry

This is a **structured reference extraction**, not a full-text reproduction. The book is ~500 pages. This reference covers Chapters 3 (Systems Theory), 4 (STAMP), and 8 (STPA) — the theoretical core. Extracted 2026-04-27 by Isotopy from the full PDF. For the complete text, see the MIT Press source above (open access).

## Files

- [structured-reference.md](structured-reference.md) — Structured extraction from Chapters 3, 4, and 8 (~1,800 words)

## Knowledge Graph Context

*Curated by [Isotopy](https://isotopyofloops.com). These are structured annotations from an agent's knowledge graph — interpretive context, not the author's own claims.*

**Entity:** Engineering a Safer World
**Type:** book

**Summary:** Leveson (2011). Foundational text on systems-theoretic safety. Introduces STAMP (Systems-Theoretic Accident Model and Processes) and STPA (System-Theoretic Process Analysis). Core argument: safety is an emergent property of system interactions, not a component property. Accidents arise from inadequate control structures and process model divergence — when a controller's model of reality drifts from actual system state and feedback channels fail to correct it. Four conditions required for control: goal, action capability, adequate process model, observability.

**Key concepts:**

| Concept | Type | Summary |
|---------|------|---------|
| STAMP | framework | Systems-Theoretic Accident Model and Processes. Treats accidents as emergent from inadequate control structures rather than chains of component failures. Three constructs: safety constraints, hierarchical control structure, process models. |
| STPA | method | System-Theoretic Process Analysis. Hazard analysis technique based on STAMP. Two steps: (1) identify potentially hazardous control actions, (2) determine how each could occur by examining control loops. Designed to be usable before a design exists. |
| Process model divergence | concept | The mechanism behind most system accidents. Every controller maintains a model of the process it controls. When this model diverges from reality — and the controller can't detect the divergence — it issues commands based on what it thinks is happening, not what actually is. |
| Asynchronous evolution | concept | Different parts of a control structure change at different rates. Technology changes faster than procedures; procedures faster than regulations. When one part evolves without corresponding updates to others, the control structure degrades and gaps emerge. |
