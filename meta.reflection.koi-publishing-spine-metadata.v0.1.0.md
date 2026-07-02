---
koi_name: meta.reflection.koi-publishing-spine-metadata.v0.1.0
relevance: core
type: reflection
subject: koi-publishing-spine-metadata
version: v0.1.0
status: draft
access: Public
format: property-based
proposes: manifesto v1.3.0
stacks_on: v1.2.0 (claude/v1.2.0-types-anchoring-examples)
---

# Proposal — KOI Publishing-Spine Metadata (manifesto v1.3.0)

**Semver impact:** minor (`v1.2.0 → v1.3.0`). Expands existing conventions; **no breaking change** — every existing KOI Name and Access value remains valid.

**Format:** property-based (Notion / YAML / JSON metadata fields), consistent with `docs/semantic-naming-properties.md`.

**Stacks on:** the pending v1.2.0 PR (`claude/v1.2.0-types-anchoring-examples`), which itself is not yet merged to `main`. Ratify v1.2.0 first, or ratify the two together.

---

## 1. Why this proposal

KOI has become the de-facto spine for RND and close-collaborator knowledge creation, and it is now being asked to serve as the canonical repository behind pluggable publishing surfaces (public web, the Murmurations/Catalist ecosystem index, commons and partner troves). Three metadata gaps block that role, and one ratified-but-undeployed vocabulary decision is still causing cross-database join failures:

1. **Access cannot express partner or personal.** The canonical scheme is three tiers (Public / Knowledge Commons / Internal). The rest of the ecosystem uses five (public / commons / partner / internal / personal). The two missing tiers are exactly the ones cooperative publishing needs: **Partner** (the close-collaborator tier) and **Personal** (the sovereignty floor that gates must exclude).
2. **Identity is decorative.** The KOI Name is a human-legible, version-mutable label — not a resolvable identity. Published records need a durable identifier that survives publication and round-trips back to the canonical object.
3. **There is no publish decision.** `Status: published` conflates "internally finished" with "cleared to emit externally," and there is no representation of *which* surface an object is approved for. Publication is currently a matter of reviewer memory, not a machine-checkable property.
4. **The canonical Vertical vocabulary was agreed but never deployed.** The 9-item Title-Case list (KOI × BizDev normalization sprint, 2026-05-04) still has not replaced the legacy 8-option ALL-CAPS KOI list, so cross-DB rollups silently break.

## 2. What this proposal changes (manifesto v1.3.0)

### Change A — Five-tier Access
Reconcile the canonical Access scheme with the RegenOS / vault / federation model: **Public · Knowledge Commons · Partner · Internal · Personal.** Public / Knowledge Commons / Internal are unchanged; Partner and Personal are added. Access is declared orthogonal to Relevance and to Publication. *(Manifesto §Access Levels.)*

### Change B — RID as a first-class property
Promote the **RID** (`orn:regen.<entity-class>:<context>/<reference>`) to a required metadata property: minted on creation, stable across renames and version bumps, emitted with every published record as the durable back-reference, and the join key between KOI Name and ledger anchor. *(Manifesto §Resource Identifier.)*

### Change C — Publication property (the publish flag)
Add a **Publication** property: a set of zero or more approved publication targets (Public Web · Open Index · Commons Trove · Partner Space), each gated by a minimum Access tier, each a separate logged decision, publish-by-decision-not-default, and never set on a Personal object. This is the machine-checkable enforcement point for the Sensitivity and Reference-Accessibility gates. *(Manifesto §Publication.)*

### Change D — Ratify the canonical Vertical vocabulary
Ratify the 9-value Title-Case Vertical list, its two retirements, and its historical alias map into [`docs/vertical-canonical-v1.md`](./docs/vertical-canonical-v1.md), and establish `docs/` as the ground-truth home for controlled vocabularies (storage surfaces are downstream mirrors). *(Manifesto §Controlled Vocabularies.)*

## 3. Semantic gaps resolved

| Gap | Before | After |
|---|---|---|
| Partner-scoped publication has no state | Folded awkwardly into "Knowledge Commons" | First-class `Partner` Access + `Partner Space` Publication target |
| Personal exclusion relies on memory | No `Personal` tier | Explicit `Personal` floor; gates exclude mechanically |
| No resolvable identity | KOI Name (mutable label) only | `RID` property, round-trip guaranteed |
| "Published" is ambiguous | `Status: published` | `Status` (editorial) + `Publication` (per-surface, gated) separated |
| Vertical joins break | 8 ALL-CAPS vs 10 mixed | One 9-value Title-Case list + alias map |

## 4. Examples (property-based)

```yaml
# A partner-scoped analysis, approved for a named partner trove
koi_name: relevant.analysis.partner-mangrove-basket-fit.v0.2.0
rid: orn:regen.artifact:koi/relevant.analysis.partner-mangrove-basket-fit.v0.2.0
relevance: relevant
access: Partner
publication: [Partner Space]
vertical: [Eco Credits]
```

```yaml
# A public overview, approved for the open ecosystem index
koi_name: core.overview.regen-registry-public.v1.0.0
rid: orn:regen.artifact:koi/core.overview.regen-registry-public.v1.0.0
relevance: core
access: Public
publication: [Public Web, Open Index]
vertical: [Eco Credits, Reporting]
```

```yaml
# A personal working note — never published
koi_name: background.notes.weekly-scratch.v0.1.0
rid: orn:regen.artifact:koi/background.notes.weekly-scratch.v0.1.0
relevance: background
access: Personal
publication: []      # P4 — Personal never publishes
```

## 5. Anticipated tradeoffs

- **More fields to set.** Two new tiers + two new properties raise per-object entry cost. Mitigation: auto-classification (koi-repo-saver) proposes defaults; humans confirm. `Publication` defaults to empty (nothing publishes without an explicit decision), so the safe default is free.
- **Migration touches multiple surfaces.** Access, Vertical, RID and Publication must be reflected across Notion (KOI Repo, Organizations DB, BizDev), Google Docs metadata blocks, GitHub frontmatter, and the publication boundary. See §6.
- **RID resolution isn't live yet.** The format is fixed now so identifiers are stable; resolution is manual until the KOI resolver ships. No re-minting later.
- **Access-tier proliferation risk.** Held at five (matching the ecosystem model); finer distinctions stay project-local within `Internal`.

## 6. Cross-surface rollout (convention level)

These metadata changes must be reflected consistently on **every KOI surface**, reconciled to the `docs/` ground truth:

1. **Notion KOI Repo** — expand `Access` to five options; add `RID` (text) and `Publication` (multi-select) properties; migrate `Vertical` to the canonical 9 with legacy aliases retained until backfilled.
2. **Related Notion DBs** — the `Vertical` change also lands on the BizDev pipeline; retirements (`PUBLIC SECTOR`, `General Tech Provider`) remap to **Actor Type** on the Organizations DB.
3. **Google Docs / GitHub frontmatter** — add `rid`, `publication`, and the five-tier `access` to the property templates in [`docs/semantic-naming-properties.md`](./docs/semantic-naming-properties.md).
4. **Publication boundary** — the RID is the identifier emitted to published records (Murmurations/Catalist and other AppViews); the `Publication` property is the gate ("labeler") that decides what leaves.

> The **surface-specific execution runbook** (field IDs, Notion DDL, backfill scripts, sequencing, and any partner-pilot specifics) is maintained as an **Internal** KOI object, not in this public repo, per the pre-push sensitivity gate. This proposal governs the *convention*; the runbook governs the *execution*.

## 7. Pilot plan (CONTRIBUTING.md: ≥2 weeks, ≥3 objects)

Pilot the five-tier Access + RID + Publication properties on at least three live objects spanning the new tiers before ratification:

1. A **Partner**-tier object approved for `Partner Space` (close-collaborator pilot — the natural first real case).
2. A **Public** object approved for `Public Web` + `Open Index`.
3. A **Personal** object carrying an RID and empty Publication (proves the exclusion path).

Success: each object carries a stable RID; the Access→Publication gate rejects every disallowed combination; and the canonical Vertical values join cleanly across KOI Repo and BizDev. Record pilot findings in this doc before merge.

## 8. Ratification checklist

- [ ] v1.2.0 PR ratified/merged (or ratified together with this)
- [ ] Governance-call review (RND + Foundation) of the five-tier Access reframe
- [ ] KOI substrate maintainer: RID format + resolver alignment with KOI substrate
- [ ] BizDev + KOI stewards: canonical Vertical sign-off (the long-pending gate) + KOI usage audit
- [ ] Pilot evidence recorded (§7)
- [ ] Manifesto v1.3.0 + `docs/vertical-canonical-v1.md` + `docs/semantic-naming-properties.md` merged; changelog updated
