---
type: decision
project: govt-case-study
date: 2026-08-28
status: decided
---

# Scope discipline via validation gates, not a fixed build-time box

**Decision:** Drop the original 9-day build constraint. The product will be AI-built; scope discipline comes from staged validation gates instead — Gate 1 requires ~20 real false-closure cases run through the appeal path before scope expands further.
**Context:** A hard 9-day deadline was the original scoping mechanism, set before the discovery phase surfaced how much validation a system-design bet like this actually needs.
**Options considered:** Keep the 9-day box and ship whatever fits; or replace it with evidence gates that run on govt-calendar time.
**Why this one (the tradeoff, one line):** Traded a fast, predictable timeline for a slower one that won't ship a false-closure fix nobody has proven works.
**Amends spec?** no — pacing decision, not a scope change.
**Revisit when:** Gate 1's ~20-case cohort completes and the appeal-path results are in.
