# KOI Regen Naming Convention Manifesto

**Version:** 1.2.0
**Status:** Active
**Maintainer:** Gregory Landua
**Last Updated:** 2026-04-21

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

| Level | Meaning |
|-------|---------|
| **Public** | Can be shared externally without restriction. |
| **Knowledge Commons** | Shared within Regen Commons participants and aligned partners. |
| **Internal** | RND internal only. |

Projects may define finer-grained sub-tiers within `Internal` (e.g., team-visible, exec-only, finance-owner-only) as project-local access policies. These do not change the canonical three-tier scheme documented here.

---

## AI Readiness

Objects marked **Ready for AI** in the KOI Repo are cleared for ingestion by Regen AI agents (registry review, CTO-in-a-box, knowledge agents). This flag indicates the content is sufficiently structured, accurate, and current to serve as context for AI-assisted workflows.

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

## Governance Process

Changes to this naming convention follow the process outlined in [CONTRIBUTING.md](./CONTRIBUTING.md):

1. **Propose** a new type, relevance level, or naming change via GitHub Issue or PR.
2. **Pilot** the proposed change in practice (minimum 2 weeks, minimum 3 objects using the new convention).
3. **Review** pilot results with maintainer and at least one other contributor.
4. **Ratify** via pull request merged to main.

---

## Changelog

See [changelog.md](./changelog.md) for the full record of changes.
