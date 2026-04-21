---
koi_name: core.spec.regen-os-learning-subroutines.v0.1.0
relevance: core
type: spec
subject: regen-os-learning-subroutines
version: v0.1.0
status: draft
access: Internal
ready_for_ai: true
created: 2026-04-21
steward: Gregory Landua
---

# RegenOS Learning Subroutines v0.1 — Atomic Closed-Loop Pattern

## Summary

The atomic primitive of RegenOS. A learning subroutine is a closed loop: **signal → capture → PACTO codification → `.md` persistence → agent consumption → strategic suggestion → new signal**. This is what turns a static `.md` file into living infrastructure.

## Why `spec` (not `docs`)

This artifact is a **precise definition of a technical pattern intended to be implemented or executed against** — not a general reference document. Three distinct subroutines are specified with identical structure (signal / capture / codification / persist / consumption / suggestion); downstream agents and humans are expected to instantiate new subroutines against this template. That is spec-nature, not docs-nature.

## Loop Definition

```
  ambient signal  ─▶  capture  ─▶  PACTO codification
  (meetings,           (Otter,      (Constitutive →
   commits,             vault,       Normative →
   edits,               inbox)       Legal stages)
   events)                             │
                                       ▼
  strategic                    canonical .md
  suggestion ◀── agent re-reads ◀── (KOI-anchored
  (weekly,      (skill, cron,         when commitment
   monthly,      agent)               threshold crossed)
   quarterly)
      │
      └─ back to ambient signal ─────────────────────────
```

**Inputs:** ambient signal + codification protocol.
**Outputs:** updated `.md` + agent-produced suggestions.
**Cadence:** per-loop varies (weekly for GTM, continuous for ops-harness, per-demo for engineering-product).

## Three Exemplar Instances

1. **GTM thesis loop** — Otter customer-discovery call → PACTO codification → `gtm-thesis.md` update → `gtm-validation-learner` re-reads → weekly GTM digest
2. **ai-ops-harness weekly retro** — Monday digest + session journals → retro-named issues → harness `.md` commit → next session inherits improvement
3. **Engineering-product Spec Gate** — Demo feedback → Spec Gate review → product-brief `.md` update → coding agent reads → shipped feature

Full details in `workspaces/RegenOS/context/learning-subroutines-v0.1.md`.

## Design Lessons (carried from gtm-validation-learner dormancy diagnosis)

1. Per-call file split kills merge conflicts
2. Rotating ownership prevents single-committer bottleneck
3. Merged PRs unblock downstream work
4. Read-only install disclaimers scare away contributors
5. CONTRIBUTING guide from day 1
6. Stale thesis is worse than no thesis — schedule forced revisitation

## Pilot Evidence

- Source workspace: `workspaces/RegenOS/context/learning-subroutines-v0.1.md`
- KOI Repo entry: https://www.notion.so/34925b77eda181629b12f471198fa76c
- Companion v1.2.0 pilots: `core.plan.regen-os-phase-delivery.v0.1.0` · `core.overview.regen-os-current-state.v0.1.0` · `core.registry.regen-os-artifact-registry.v0.1.0`

## Revision Trigger

After first end-to-end loop runs · after a new candidate subroutine is stewarded · after a dormancy pattern is diagnosed in a live subroutine.

## Kill Criterion

If by end of Phase 2 (end-of-April 2026) none of the three exemplar subroutines has closed one end-to-end loop, the subroutine pattern is not yet the right primitive — revisit as a batch-processing model instead of per-loop.
