# KOI Naming Convention Changelog

All notable changes to the KOI naming conventions are documented here.

Format follows [Keep a Changelog](https://keepachangelog.com/).

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
