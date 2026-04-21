---
koi_name: core.overview.regen-os-current-state.v0.1.0
relevance: core
type: overview
subject: regen-os-current-state
version: v0.1.0
status: draft
access: Internal
ready_for_ai: true
created: 2026-04-21
steward: Gregory Landua
---

# RegenOS Current State — Overview (2026-04-21 snapshot)

## Summary

Canonical explainer of RegenOS as of 2026-04-21 builders-standup prep. RegenOS is the **pointer + learning-protocol layer** that unifies RND PBC's already-in-place infrastructure (agentic harness, BizDev, product engineering, ops/finance, knowledge commons) into a coherent but heterogeneously-permissioned fabric we dogfood on ourselves.

## Why `overview` (not `readme` or `strategy`)

- Not a `readme` — this file is not the entry-point navigation for a specific directory or repo; it's an explainer of a system's current state
- Not a `strategy` — this is a point-in-time snapshot of what exists and how it coheres, not a forward-looking plan (that lives in `core.plan.regen-os-phase-delivery.v0.1.0`)
- Not a `memo` — memos originate a position; overviews describe a state

## What RegenOS Is

- **Unified**: integrates agentic harness (`ai-ops-finance-harness` + `regen-ai-core`), BizDev pipeline, product engineering, ops/finance, knowledge commons
- **Lean**: not waterfall — every artifact names revision trigger + kill criterion
- **Continuously-learning**: through learning subroutines (signal → codification → `.md` → agent → suggestion)
- **Heterogeneously permissioned**: team-visible default; exec / finance-owner / HR-personal tiers
- **Content-addressable**: every reference resolves via IRI / URL / RID; high-commitment artifacts anchored to Regen Ledger
- **Dogfooded**: we run what we sell — 4 mainnet anchors on `regen-1`, Monday digest agent-produced, 33 skills live

## Architecture (at a glance)

Five integration axes × seven lenses × three working primitives:

- **Axes** — agentic harness · BizDev pipeline · product engineering · ops/finance/HR · strategy & objective-function clusters
- **Lenses** — heptad · claims engine · ledger · web app / demo pipeline · OPAL coherence · PACTO · Becca/Dave triad
- **Primitives** — learning subroutines · sensor pipeline · versioning protocol

## What's Live Today (empirical)

- 🟢 Four-Surface ops harness + `regen-signing` shipped 2026-04-17 + 4 mainnet anchors + 33 skills + KOI MCP + Monday digest
- 🟡 `gtm-validation-learner` scaffolded-but-dormant (6 diagnosed root causes, structural fix pending)
- 🔵 `claims-engine-unit-economics` research charter; liability/underwriting discovery pipeline (speculative, 7-month verdict)

## Pilot Evidence

- Source workspace: `workspaces/RegenOS/context/regen-os-overview-v0.1.md`
- KOI Repo canonical-strategy entry: `core.strategy.regen-os-overview.v0.1.0` (https://www.notion.so/34925b77eda18173b759f906ba2c54a5) — same content, different frame (strategy = forward-looking; overview = current-state snapshot). The two types complement; an overview gets superseded by the next overview, while a strategy evolves version-by-version.
- Companion v1.2.0 pilots: `core.spec.regen-os-learning-subroutines.v0.1.0` · `core.plan.regen-os-phase-delivery.v0.1.0` · `core.registry.regen-os-artifact-registry.v0.1.0`

## Revision Trigger

Any new integration axis added · any of the 5 currently-live or 3 dormant/speculative systems materially shifts status · quarterly snapshot refresh.

## Kill Criterion

If this overview is not the reliable "what is RegenOS" landing page for new team members after Phase 2 (end of April), the `overview` type isn't earning its keep — fold back into `readme` or `strategy`.
