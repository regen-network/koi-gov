# KOI Regen Naming Convention Manifesto

**Version:** 1.1.0
**Status:** Active
**Maintainer:** Gregory Landua
**Last Updated:** February 12, 2026

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
core.memo.token-utility-framework.v2.0.0
relevant.analysis.terrasos-deal-structure.v1.1.0
background.notes.ecosystem-partner-landscape.v0.3.1
core.strategy.regen-business-model.v1.0.0
relevant.research.aimma-regulatory-landscape.v1.0.0
```

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

The following types emerged from active KOI usage across Regen Network's operational and strategic work. They were previously tracked in the Notion KOI Repo but not codified in this manifesto.

| Type | Description | When to Use |
|------|-------------|-------------|
| `strategy` | Forward-looking strategic framework or business model. | GTM plans, business models, roadmaps, investment narratives. |
| `docs` | Reference documentation, specifications, or guides. | Technical specs, API docs, process documentation, handbooks. |
| `feedback` | Structured feedback on proposals, products, or processes. | Review responses, partner feedback, user research findings. |
| `research` | Investigative or exploratory research output. | Market research, regulatory landscape scans, technology assessments. |
| `press` | External-facing communications and media materials. | Blog posts, press releases, public statements, media briefs. |
| `prompt` | AI prompt templates, agent configurations, or instruction sets. | System prompts, skill definitions, agent specs, prompt libraries. |
| `transcript` | Meeting or conversation transcript, typically AI-generated. | Otter.ai transcripts, call recordings, interview records. |

### Deprecated Types

| Type | Status | Notes |
|------|--------|-------|
| Final Analysis | Deprecated — use `analysis` instead. | Was used in Notion KOI Repo as a status marker. Use `analysis` as the type and track completion status separately via the Status field. |

---

## Choosing Between Types

When the distinction is ambiguous:

- **memo vs strategy**: Memos communicate a position or proposal; strategies lay out a forward-looking plan with phases, milestones, or resource requirements.
- **analysis vs research**: Analyses evaluate a specific question or decision; research explores a domain or landscape more broadly.
- **docs vs readme**: Readmes are entry-point documentation for a specific directory or system; docs are standalone reference materials.
- **notes vs transcript**: Notes are human-authored (even if rough); transcripts are machine-generated or verbatim records.
- **feedback vs memo**: Feedback responds to something specific; memos originate a position.

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

---

## AI Readiness

Objects marked **Ready for AI** in the KOI Repo are cleared for ingestion by Regen AI agents (registry review, CTO-in-a-box, knowledge agents). This flag indicates the content is sufficiently structured, accurate, and current to serve as context for AI-assisted workflows.

---

## Governance Process

Changes to this naming convention follow the process outlined in [CONTRIBUTING.md](./CONTRIBUTING.md):

1. **Propose** a new type, relevance level, or naming change via GitHub Issue.
2. **Pilot** the proposed change in practice (minimum 2 weeks, minimum 3 objects using the new convention).
3. **Review** pilot results with maintainer and at least one other contributor.
4. **Ratify** via pull request merged to main.

---

## Changelog

See [changelog.md](./changelog.md) for the full record of changes.
