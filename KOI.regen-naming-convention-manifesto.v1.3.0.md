# KOI Regen Naming Convention Manifesto

**Version:** 1.3.0
**Status:** Proposed — pending governance-call ratification
**Maintainer:** Gregory Landua
**Last Updated:** 2026-07-01

> **v1.3.0 note.** This version stacks on the pending v1.2.0 PR (`claude/v1.2.0-types-anchoring-examples`) and adds the **publishing-spine metadata layer**: a five-tier Access scheme aligned with the RegenOS access model, a first-class **RID** identity property, a **Publication** (per-surface publish decision) property, and ratification of the canonical **Vertical** controlled vocabulary. v1.2.0 should be ratified/merged first, or the two ratified together. No existing KOI name is invalidated.

---

## Purpose

This document defines the canonical semantic naming conventions for KOI (Knowledge Organizing Infrastructure) objects within Regen Network. These conventions enable coherent coordination between distributed teams, AI agents, and community participants.

---

## Naming Structure

```
[relevance].[type].[subject].vX.Y.Z
```

### Examples

```
core.strategy.regen-os-overview.v0.1.0
core.spec.regen-os-learning-subroutines.v0.1.0
core.plan.regen-os-phase-delivery.v0.1.0
core.registry.regen-os-artifact-registry.v0.1.0
core.overview.regen-commons-current-state.v0.1.0
relevant.analysis.distribution-moat-dual-framework.v1.0.0
relevant.research.aimma-regulatory-landscape.v1.0.0
background.notes.ecosystem-partner-landscape.v0.3.1
```

See [`examples/`](./examples/) for worked examples of each v1.2.0 type.

---

## Relevance Levels

| Level | Meaning | Typical Use |
|-------|---------|-------------|
| `core` | Fundamental, actively used, essential to strategic decisions. | Active strategy docs, governance frameworks, canonical references. |
| `relevant` | Informative, actively cited, influential in ongoing work. | Supporting analyses, partner-specific materials, active research. |
| `background` | Contextual, supportive, historical, or ambient reference. | Archived decisions, historical context, exploratory notes. |

---

## Object Types

### Original Types (v1.0.0)

| Type | Description | When to Use |
|------|-------------|-------------|
| `memo` | Structured strategic or operational document. | Formal communication, position papers, internal proposals. |
| `analysis` | Data-driven or qualitative deep dive. | Market analysis, deal modeling, technical evaluation. |
| `notes` | Informal or exploratory ideas and documentation. | Meeting notes, brainstorms, working drafts. |
| `decision` | Official organizational decision record. | Governance votes, strategic commitments, policy changes. |
| `readme` | Canonical documentation for directories or patterns. | Repository docs, onboarding guides, system overviews. |

### Expanded Types (v1.1.0)

Codified in v1.1.0 from active Notion KOI Repo usage.

| Type | Description | When to Use |
|------|-------------|-------------|
| `strategy` | Forward-looking strategic framework or business model. | GTM plans, business models, roadmaps, investment narratives. |
| `docs` | Reference documentation, specifications, or guides. | Technical specs, API docs, process documentation, handbooks. |
| `feedback` | Structured feedback on proposals, products, or processes. | Review responses, partner feedback, user research findings. |
| `research` | Investigative or exploratory research output. | Market research, regulatory landscape scans, technology assessments. |
| `press` | External-facing communications and media materials. | Blog posts, press releases, public statements, media briefs. |
| `prompt` | AI prompt templates, agent configurations, or instruction sets. | System prompts, skill definitions, agent specs, prompt libraries. |
| `transcript` | Meeting or conversation transcript, typically AI-generated. | Otter.ai transcripts, call recordings, interview records. |

### Expanded Types (v1.2.0)

The following types emerged from active use cases that had no clean home in v1.1.0. Each is grounded in a concrete RegenOS artifact or mainnet-anchored artifact; see [`examples/`](./examples/) for the worked pilots satisfying the CONTRIBUTING.md minimum-3-object pilot requirement.

| Type | Description | When to Use | Pilot |
|------|-------------|-------------|-------|
| `spec` | Technical specification, agentic loop spec, pattern specification, or agent instruction template. | Agent loop definitions, pattern specs, schema specs, protocol specifications that aren't general `docs`. | `core.spec.regen-os-learning-subroutines.v0.1.0` |
| `plan` | Phased execution plan with milestones, gates, and resource requirements. | Dogfood plans, discovery pipelines, phased delivery plans distinct from forward-looking `strategy`. | `core.plan.regen-os-phase-delivery.v0.1.0` |
| `overview` | Canonical explainer of a system or domain at a point in time. | Top-level explainers that aren't directory entry points (`readme`) and aren't forward-looking (`strategy`). | `core.overview.regen-os-current-state.v0.1.0` |
| `registry` | Meta-document that indexes or directories other knowledge objects. | Artifact registries, URL/RID maps, schema libraries, catalog indexes distinct from reference `docs`. | `core.registry.regen-os-artifact-registry.v0.1.0` |

### Deprecated Types

| Type | Status | Notes |
|------|--------|-------|
| Final Analysis | Deprecated — use `analysis` instead. | Was used in Notion KOI Repo as a status marker. Use `analysis` as the type and track completion status separately via the Status field. |

---

## Choosing Between Types

When the distinction is ambiguous:

- **memo vs strategy** — Memos communicate a position or proposal; strategies lay out a forward-looking plan with phases, milestones, or resource requirements.
- **analysis vs research** — Analyses evaluate a specific question or decision; research explores a domain or landscape more broadly.
- **docs vs readme** — Readmes are entry-point documentation for a specific directory or system; docs are standalone reference materials.
- **docs vs spec** — Docs are general reference material; specs are precise definitions of a technical artifact, agent loop, or pattern intended to be implemented or executed against.
- **docs vs registry** — Docs describe a thing; registries index many things. A registry's primary content is the index itself, not the content of what's indexed.
- **strategy vs plan** — Strategy is the framework (why + what); plan is the execution sequence (when + who + gates). A strategy contains a plan; a plan operationalizes a strategy.
- **readme vs overview** — Readmes are entry-points to a directory/repo (how to navigate this place); overviews are explainers of a system/domain (what this system is and how it works). A readme answers "start here"; an overview answers "what is this?"
- **notes vs transcript** — Notes are human-authored (even if rough); transcripts are machine-generated or verbatim records.
- **feedback vs memo** — Feedback responds to something specific; memos originate a position.

---

## Semantic Versioning

KOI objects use semantic versioning to track conceptual evolution:

| Version Component | Meaning | Example |
|-------------------|---------|---------|
| `vX.0.0` (major) | Fundamental conceptual shift, reframe, or restructure. | v1.0.0 → v2.0.0: complete rethinking of token utility model. |
| `vX.Y.0` (minor) | Meaningful content update, new sections, revised conclusions. | v1.0.0 → v1.1.0: added new business line, updated revenue projections. |
| `vX.Y.Z` (patch) | Editorial fixes, formatting, typos, non-conceptual changes. | v1.1.0 → v1.1.1: fixed table formatting, corrected a date. |

### Versioning Guidelines

- A new object starts at `v1.0.0` (or `v0.1.0` if explicitly draft/experimental).
- Increment the major version when the core thesis or framework changes.
- Increment the minor version when substantive content is added or revised.
- Increment the patch version for editorial or cosmetic changes only.
- Version numbers apply to the content, not the file. Renaming or moving a file does not require a version bump.
- Ledger-anchored versions are immutable once anchored (see §Ledger Anchoring). A version bump produces a new anchor, not a modification of the prior one.

---

## Status Tracking

KOI objects carry a **Status** field (tracked in Notion, not encoded in the filename):

| Status | Meaning |
|--------|---------|
| `draft` | Work in progress, not yet reviewed. |
| `in review` | Under active review by stakeholders. |
| `ready to publish` | Reviewed and approved, awaiting publication. |
| `published` | Final, externally shareable. |

---

## Access Levels

KOI objects carry an **Access** level that governs *who may see the object*. As of v1.3.0 the canonical scheme is **five tiers**, aligned one-to-one with the RegenOS / Regen Commons access model so that a single access value means the same thing across the vault, the wiki, the KOI Repo, and every downstream publishing surface.

| Level | Meaning | Audience |
|-------|---------|----------|
| **Public** | Shareable externally without restriction. | Anyone. |
| **Knowledge Commons** | Shareable within Regen Commons participants and aligned community contributors. | Community / commons contributors. |
| **Partner** | Shareable with a **named, invited** partner organization under explicit, per-partner approval. | Invited partner orgs. |
| **Internal** | RND PBC + core contributors only. | RND internal. |
| **Personal** | Local / individual only; **never federated or published**. This is the sovereignty floor. | The author. |

### Why five tiers (v1.3.0 change)

Prior to v1.3.0 the manifesto codified three tiers and treated finer distinctions as "project-local policies." In practice the rest of the ecosystem (RegenOS access model, the Reference-Accessibility Gate, the Federation Layer consent envelope, the vault/wiki `access:` frontmatter) uses **five tiers**, and the three-tier scheme could not express the two cases that matter most for cooperative publishing:

- **Partner** — the "close-collaborator" tier. Publishing a knowledge object to a *named* partner (or a partner-scoped surface such as a Catalist/Murmurations trove) is a distinct decision from publishing to the open commons. Without a `Partner` tier, partner-scoped publication has no representable state.
- **Personal** — the sovereignty floor. Making `Personal` explicit lets automated gates *exclude* it mechanically rather than by reviewer memory.

### Mapping to the workspace access model

| KOI Access | RegenOS / vault `access:` | Federation consent envelope |
|---|---|---|
| Public | `public` | `public` |
| Knowledge Commons | `commons` | `commons` |
| Partner | `partner` | `partner` |
| Internal | `internal` | `internal` |
| Personal | `personal` | `personal` |

### Migration note

`Public`, `Knowledge Commons`, and `Internal` are unchanged — every existing object keeps its Access value. `Partner` and `Personal` are **added**. Objects previously stretched to fit (e.g., a partner-shared doc marked `Knowledge Commons`, or a personal note marked `Internal`) should be re-tagged during the metadata upgrade (see the controlled-vocabulary and rollout guidance). Projects may still define finer sub-tiers *within* `Internal` (team-visible, exec-only, finance-owner-only) as project-local policies; these do not change the canonical five-tier scheme.

### Access is orthogonal to Relevance and to Publication

Three independent axes, each answering a different question:

- **Access** — *who may see this?* (sensitivity)
- **Relevance** — *how foundational is this?* (`core` / `relevant` / `background`)
- **Publication** — *has this been approved to emit to a specific external surface?* (see §Publication below)

A `core` object may be `Personal`; a `Public` object may be `background`; an `Internal` object is never published to any external surface regardless of Relevance. Do not collapse these axes.

---

## AI Readiness

Objects marked **Ready for AI** in the KOI Repo are cleared for ingestion by Regen AI agents (registry review, CTO-in-a-box, knowledge agents). This flag indicates the content is sufficiently structured, accurate, and current to serve as context for AI-assisted workflows.

---

## Publication (v1.3.0)

**Access says who *may* see an object. Publication says whether it has been *approved to emit* to a specific external surface, and to which one.** These are different decisions and must not be conflated with `Status` (which tracks internal editorial lifecycle) or with `Access` (which tracks sensitivity).

The **Publication** property is a set of zero or more publication targets. An object with no publication target is not published anywhere, regardless of its `Status` or `Access`.

| Publication target | Meaning | Minimum Access required |
|---|---|---|
| *(none)* | Not published to any external surface. Default. | — |
| **Public Web** | Rendered on a public Regen surface (site, public wiki, public Notion). | Public |
| **Open Index** | Emitted to the public ecosystem index (Murmurations / Catalist / Arcos public trove). | Public |
| **Commons Trove** | Emitted to a Regen Commons / community-scoped trove. | Knowledge Commons |
| **Partner Space** | Emitted to a **named** partner surface under explicit approval. | Partner |

### Rules

- **P1 — Publish-by-decision, not by default.** An object is published only if a human or governance process sets a Publication target. `Status: published` alone does **not** authorize any external emit.
- **P2 — Access is the ceiling.** A target may be set only if the object's Access permits it (see table). The gate rejects, e.g., an `Internal` object with any Publication target, and a `Public` object may still carry *no* target.
- **P3 — Per-surface consent.** Approving `Commons Trove` does not approve `Open Index`. Each target is a separate decision, logged with (RID, target, timestamp, approver).
- **P4 — Personal never publishes.** A `Personal` object can carry no Publication target under any circumstances.
- **P5 — Governance of the flag.** Who may set a Publication target is a governed decision (steward / council / automated policy). Projects define the setter; the *existence and semantics* of the property are canonical.

The Publication property is the machine-checkable point where the Sensitivity and Reference-Accessibility gates are enforced structurally rather than by reviewer memory. It is the "labeler" in the publication-adapter architecture (KOI → Catalist/Murmurations and other AppViews).

---

## Resource Identifier (RID) (v1.3.0)

The **KOI Name** (`[relevance].[type].[subject].vX.Y.Z`) is a human-legible, mutable-by-versioning label. It is **not** a resolvable identity. v1.3.0 promotes the **RID** to a first-class metadata property: the durable, resolvable identifier that survives publication, federation, and cross-surface reference.

### Format

```
orn:regen.<entity-class>:<context>/<reference>
```

Examples:

```
orn:regen.document:notion/<page-uuid>
orn:regen.artifact:koi/core.overview.regen-os-current-state.v0.1.0
orn:regen.entity:org/regen-network
```

### Rules

- **RID-1 — Every KOI object has an RID.** It is minted on creation and is stable for the life of the object across renames and version bumps.
- **RID-2 — RID is the identity that travels.** When an object is published to any surface (Publication targets above), the RID is emitted with it as the durable back-reference. This is the DID-equivalent in the AT-Protocol-analogy publication model: presentation surfaces are replaceable; the RID is not.
- **RID-3 — Round-trip requirement.** Any external reference or read-back MUST resolve through the RID back to the canonical KOI object. A published profile that drops its RID is non-conformant.
- **RID-4 — RID ≠ KOI Name ≠ ledger anchor.** The RID resolves the *object*; the KOI Name *labels a version* of it; a ledger anchor (below) *proves the content* of a specific version. An object may have all three; the RID is the join key.
- **RID-5 — Resolution.** The RID resolves via the KOI resolver (see the knowledge-accessibility pipeline). Until the resolver is live, the RID is recorded as a metadata property and resolution is manual; the format is fixed now so no re-minting is needed later.

---

## Ledger Anchoring

Any KOI object whose content represents a **commitment-threshold artifact** — a decision, a plan, a public-facing claim, an externally-verifiable deliverable — can be elevated to a content-addressable Regen Ledger Resource Identifier (RID) via an on-chain anchor.

### When to Anchor

Anchor a KOI object when at least one of the following applies:

- The object records an organizational commitment that should be immutably auditable (decisions, published plans, governance outcomes)
- The object will be cited by downstream agents or contracts that need content-addressable resolution
- The object is an externally-verifiable claim (anchored insights, attested analyses, published research)
- The object is a schema or specification that downstream tooling must pin against

### How to Anchor

Anchoring produces a **triad** of on-chain and off-chain artifacts:

| Artifact | Location | Purpose |
|---|---|---|
| `*.canonical.json` | local + anchored hash | the exact content that was hashed |
| `*.manifest.json` | local + anchored hash | metadata about the canonical content (author, date, workspace path, KOI Name) |
| `*.receipt.md` | local | the receipt of the anchoring transaction (tx hash, ledger height, block time) |

The anchoring is performed via the Regen Ledger `x/data` module's `MsgAnchor` transaction. The `regen-signing` skill (in `regen-ai-core`) orchestrates the canonical → manifest → signing → receipt flow.

### Post-Anchor Rules

Once an object is anchored at a specific version:

- **The anchored canonical.json is immutable at that hash.** It is never modified in place.
- **Renaming the file modifies its content hash** if the path is part of the canonical serialization, invalidating the on-chain anchor. Anchored files are therefore rename-hostile — see §Rename Discipline below.
- **Version bumps produce new anchors.** A `v0.1.0` → `v0.2.0` upgrade requires a new canonical/manifest/receipt triad and a new `MsgAnchor` transaction.
- **Historical anchors are preserved.** Do not delete or overwrite the canonical/manifest/receipt files for prior versions; they are the authoritative record of what was committed.

### Rename Discipline

Before any bulk text operation (folder rename, mass find-and-replace, automated migration) that might touch anchored files:

1. **Inventory** — identify all anchored canonical/manifest/receipt files in scope
2. **Classify** each candidate file as:
   - `anchored-historical` — SKIP (record preserves the original path forever)
   - `forward-reference only` — UPDATE (text operation is safe)
   - `anchored-living` — RE-ANCHOR (version bump + changelog + new anchor triad)
3. **Operate** on the non-anchored set only
4. **Verify** — re-grep to confirm anchored files' references are unchanged

Failure mode warning: a rename that invalidates an anchor produces no error. The file still exists, still parses, still renders — the on-chain anchor simply no longer resolves. Detection is downstream (verification query fails) and often much later.

### Legacy Names

Some objects anchored prior to v1.2.0 ratification use a **non-canonical first field** (e.g., `strategy.plan.claims-engine-dogfood-plan.v0.1.0` where `strategy` is neither a canonical relevance nor type). These legacy names are preserved as historical record — the ledger anchor is the authoritative identity of the object, and the on-chain record cannot be retroactively corrected without invalidating the anchor.

Going forward (v1.2.0+), all new anchored objects must use canonical `[relevance].[type].[subject].vX.Y.Z`. Legacy objects are grandfathered and should be cross-indexed to canonical names in the artifact registry (if applicable) but never renamed on-chain.

---

## Controlled Vocabularies (v1.3.0)

Beyond the KOI Name grammar, KOI objects carry **classification properties** whose allowed values are controlled vocabularies (L0). These vocabularies are canonical here so that the same value means the same thing across the KOI Repo, the BizDev pipeline, the Organizations DB, and any published record.

- **Vertical** — the market-context taxonomy. The canonical v1 list (9 values, Title Case), the retirements, and the historical alias map for backfill are ratified in [`docs/vertical-canonical-v1.md`](./docs/vertical-canonical-v1.md). This supersedes the legacy ALL-CAPS 8-option KOI list and the divergent 10-option BizDev list.
- **Relevance** — `core` / `relevant` / `background` (see §Relevance Levels).
- **Access** — the five tiers (see §Access Levels).
- **Publication** — the publication targets (see §Publication).

**Vocabulary governance.** A controlled vocabulary changes by the same propose → pilot → ratify process as the naming convention. New values, retirements, and casing conventions are recorded in the vocabulary's doc under `docs/`, with an alias map whenever a change requires backfill. Casing is **Title Case** for all vocabulary values unless a value is a proper acronym.

**Where the ground truth lives.** A controlled vocabulary's authoritative source is its `docs/` file in this repo. Storage surfaces (Notion option-sets, BizDev fields, RDF class instances) are downstream *mirrors* of that source and are reconciled to it during metadata upgrades — never the other way around.

---

## Governance Process

Changes to this naming convention follow the process outlined in [CONTRIBUTING.md](./CONTRIBUTING.md):

1. **Propose** a new type, relevance level, or naming change via GitHub Issue or PR.
2. **Pilot** the proposed change in practice (minimum 2 weeks, minimum 3 objects using the new convention).
3. **Review** pilot results with maintainer and at least one other contributor.
4. **Ratify** via pull request merged to main.

---

## Changelog

See [changelog.md](./changelog.md) for the full record of changes.
