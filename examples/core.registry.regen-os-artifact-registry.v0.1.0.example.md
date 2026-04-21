---
koi_name: core.registry.regen-os-artifact-registry.v0.1.0
relevance: core
type: registry
subject: regen-os-artifact-registry
version: v0.1.0
status: draft
access: Internal
ready_for_ai: true
created: 2026-04-21
steward: Gregory Landua
---

# RegenOS Knowledge Artifact Registry v0.1 — IRI/URL/RID Map

## Summary

Index of 45 knowledge artifacts across 9 sections, each with canonical URL, access tier, steward, and update cadence. Every RegenOS artifact must cite from or add to this registry — workspace-path-only references are never sufficient for non-personal audiences (Reference Accessibility Gate).

## Why `registry` (not `docs`)

- The primary content of this artifact **is the index itself** — not the content of what's indexed
- Downstream agents and humans use it as a lookup table, not as reference documentation
- Updates follow an "add a row" cadence, not a "revise the prose" cadence
- `docs` describe a thing; `registry` indexes many things

## Structure

Each row carries six fields:

| Field | Purpose |
|---|---|
| Artifact | Short identifier |
| Canonical URL | Resolvable surface for the artifact |
| RID | Regen Ledger resource identifier (if anchored) |
| Access tier | team / exec / finance / personal / client |
| Steward | Named human responsible for keeping it current |
| Cadence | How often updates are expected |

## Sections

The registry is organized into 9 sections:

1. Agentic harness repos (`ai-ops-finance-harness`, `regen-ai-core`, contexts/, skills/)
2. Business development (BizDev pipeline, GTM thesis, Becca/Dave triad docs)
3. Product engineering (process page, spec gate, demo-to-spec)
4. Ops / Finance / HR (restricted-access, exec and finance-owner tiers)
5. Strategy & objective-function clusters
6. Frameworks & lenses (heptad, PACTO, OPAL, Coherence Protocol)
7. Knowledge commons & ledger substrate (KOI Notion Repo, KOI MCP, Heartbeat, `regen-1`, regen-signing, 4 mainnet anchors)
8. Personal & session layers (vault/, inbox/, session journals, auto-memory)
9. RegenOS self-references (CLAUDE.md, overview, swim lane, subroutines, schema library, deck)

## RID Status

All 45 entries currently carry `[NO RID YET]` in the RID column. Phase 1 pilot (this week) selects 3–5 high-use artifacts to elevate to RID-bearing status via the `regen-signing` skill — first RegenOS ledger anchor target for Phase 2 (end-of-April).

## Pilot Evidence

- Source workspace: `workspaces/RegenOS/context/knowledge-artifact-registry-v0.1.md`
- KOI Repo entry: https://www.notion.so/34925b77eda1812ca4efc382858bf1a7
- Companion v1.2.0 pilots: `core.spec.regen-os-learning-subroutines.v0.1.0` · `core.plan.regen-os-phase-delivery.v0.1.0` · `core.overview.regen-os-current-state.v0.1.0`

## Revision Trigger

Any new integration surface added to RegenOS · any artifact promoted to RID-bearing · quarterly steward review.

## Kill Criterion

If by end of Phase 1 (this week) fewer than 5 artifacts have RIDs, content-addressing discipline is decorative rather than operational — escalate at Phase 2 all-hands and either re-scope or retire the discipline.
