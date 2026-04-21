---
koi_name: core.plan.regen-os-phase-delivery.v0.1.0
relevance: core
type: plan
subject: regen-os-phase-delivery
version: v0.1.0
status: draft
access: Internal
ready_for_ai: true
created: 2026-04-21
steward: Gregory Landua
---

# RegenOS Phased Delivery Plan v0.1

## Summary

Phased execution plan for RegenOS — the unified, lean, continuously-learning operating system for RND PBC. Five phases from scaffolding (today) through steady-state OKRs (June 2026), each with explicit gates and kill criteria.

## Why `plan` (not `strategy`)

This artifact is the **execution sequence** (when + who + gates), not the forward-looking framework (why + what). The strategy lives in `core.strategy.regen-os-overview.v0.1.0`; this plan operationalizes it.

## Phases

| Phase | When | Delivery | Gate to next |
|---|---|---|---|
| 0 | 2026-04-21 (today) | CLAUDE.md + 6 context artifacts (overview · registry · swim lane · subroutines · schema catalog · deck) | ICs confirm swim-lane stewardship |
| 1 | this week (ICs) | GitHub repo scoped (team-visible default); Notion dashboard spec; stewards confirmed | Repo approved + dashboard spec signed off |
| 2 | end of April (all-hands) | `regen-network/regen-os` repo live; Notion dashboard skeleton; first closed subroutine loop; first RegenOS ledger anchor | First subroutine loop closes end-to-end |
| 3 | May | Unified Notion dashboard live with heterogeneous permission views; sensor pipeline proven for 1 strategic-upgrade class | Sensor pipeline produces 1 actionable upgrade memo |
| 4 | June | Singular RND-wide OKRs derived via PACTO; steady-state OS; quarterly refresh cadence | — (steady state) |

## Resource Requirements

- Gregory (steward, orchestrator) — active all phases
- ICs (role-specific stewards) — Phase 1 onward
- Dave (COO, BizDev) — Phase 1 onward for stewardship validation
- Marie + Darren (product engineering) — Phase 1 onward
- Christian (CFO ops) · Mark (finance) — Phase 2+ for exec/finance-owner tier integration

## Kill Criterion

If after Phase 1 no ICs have volunteered swim-lane stewardship, RegenOS framing is not resonating — pause before Phase 2 and restructure the deck/narrative.

## Revision Trigger

Post-standup feedback · any phase gate missed by more than one week · addition of a sixth integration axis.

## Pilot Evidence

- Source workspace: `workspaces/RegenOS/context/regen-os-overview-v0.1.md` §Phased Delivery
- Builders-standup deck Slide 5 (Candidate Product Roadmap) includes this plan's Track A
- Companion v1.2.0 pilots: `core.spec.regen-os-learning-subroutines.v0.1.0` · `core.overview.regen-os-current-state.v0.1.0` · `core.registry.regen-os-artifact-registry.v0.1.0`
