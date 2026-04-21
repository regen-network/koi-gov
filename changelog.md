# KOI Naming Convention Changelog

All notable changes to the KOI naming conventions are documented here.

Format follows [Keep a Changelog](https://keepachangelog.com/).

---

## [1.2.0] - 2026-04-21

### Added

- 4 new object types codified from concrete use-cases that had no clean home in v1.1.0:
  - **spec** — technical specification, agentic loop spec, pattern spec, or agent instruction template
  - **plan** — phased execution plan with milestones, gates, and resource requirements (distinct from forward-looking `strategy`)
  - **overview** — canonical explainer of a system or domain at a point in time (distinct from entry-point `readme` and forward-looking `strategy`)
  - **registry** — meta-document that indexes or directories other knowledge objects (distinct from reference `docs`)
- **§Ledger Anchoring** section in manifesto — when to anchor, how to anchor (canonical/manifest/receipt triad via `MsgAnchor`), post-anchor rules, rename discipline (classification procedure for bulk operations), and §Legacy Names guidance for pre-v1.2.0 non-canonical anchors
- **examples/ directory** — worked examples demonstrating each v1.2.0 type, satisfying CONTRIBUTING.md minimum-3-object pilot requirement
- **"Choosing Between Types" guidance** extended with v1.2.0 pairs: `docs vs spec`, `docs vs registry`, `strategy vs plan`, `readme vs overview`
- Note in Access Levels section clarifying that projects may define finer-grained sub-tiers (team-visible, exec-only, finance-owner-only) as project-local access policies without changing the canonical three-tier scheme

### Fixed

- `docs/semantic-naming-properties.md` example had multiple issues: undefined type `objective`, double-version suffix `v2025-Q2.v0.1.4`, undefined status `active`. Replaced with canonical `core.strategy.regen-os-overview.v0.1.0` example across all three occurrences (Notion property table, Google Docs metadata block, GitHub YAML frontmatter)
- `CONTRIBUTING.md` "Who Can Contribute?" heading was missing the `##` prefix, breaking the section's Markdown rendering. Heading restored.

### Pilot Evidence (CONTRIBUTING.md minimum-3-object requirement)

Four RegenOS Phase 0 artifacts (2026-04-21 builders-standup prep session) serve as the pilot set — one per new type:

- `core.spec.regen-os-learning-subroutines.v0.1.0` — atomic closed-loop pattern specification
- `core.plan.regen-os-phase-delivery.v0.1.0` — 5-phase execution plan from scaffolding through singular OKRs
- `core.overview.regen-os-current-state.v0.1.0` — point-in-time explainer of RegenOS
- `core.registry.regen-os-artifact-registry.v0.1.0` — 45-artifact IRI/URL/RID index

Additional evidence for §Ledger Anchoring section: 4 mainnet anchors on `regen-1` (2026-04-17/18) produced via `regen-signing` skill; pre-v1.2.0 legacy anchor `strategy.plan.claims-engine-dogfood-plan.v0.1.0` cited as the §Legacy Names case study.

### Notes

- Manifesto version bumped from v1.1.0 to v1.2.0. `KOI.regen-naming-convention-manifesto.v1.1.0.md` preserved as historical record.
- No breaking changes. All existing v1.0.0 and v1.1.0 names remain valid.
- §Legacy Names explicitly grandfathers on-chain anchors predating v1.2.0 that use non-canonical first fields — these cannot be "fixed" retroactively without invalidating the anchor.

---

## [1.1.0] - 2026-02-12

### Added

- 7 new object types codified from active Notion KOI Repo usage:
  - **strategy** — forward-looking strategic frameworks and business models
  - **docs** — reference documentation, specifications, and guides
  - **feedback** — structured feedback on proposals, products, or processes
  - **research** — investigative or exploratory research output
  - **press** — external-facing communications and media materials
  - **prompt** — AI prompt templates, agent configurations, instruction sets
  - **transcript** — meeting or conversation transcripts, typically AI-generated
- "Choosing Between Types" guidance for disambiguating similar object types
- Status tracking section documenting the draft → in review → ready to publish → published lifecycle
- Access levels section documenting Public / Knowledge Commons / Internal tiers
- AI Readiness section documenting the Ready for AI flag for agent ingestion
- Versioning guidelines with concrete examples and rules for when to bump each component

### Deprecated

- **Final Analysis** object type — use `analysis` with appropriate Status field instead

### Changed

- Manifesto version bumped from v1.0.0 to v1.1.0
- Expanded examples in naming structure section to include new types
- Object Types section reorganized into Original (v1.0.0), Expanded (v1.1.0), and Deprecated subsections

### Notes

- These types were already in active use in the Notion KOI Repo database but had not been formally codified in the manifesto. This update brings the canonical specification into alignment with actual practice.
- No breaking changes. All existing v1.0.0 names remain valid.

---

## [1.0.0] - 2025-04-14

### Added

- Initial KOI naming convention manifesto
- Core naming structure: `[relevance].[type].[subject].vX.Y.Z`
- Three relevance levels: `core`, `relevant`, `background`
- Five object types: `memo`, `analysis`, `notes`, `decision`, `readme`
- Semantic versioning scheme for KOI objects
- Governance process for proposing and ratifying changes
- CONTRIBUTING.md with contribution guidelines
