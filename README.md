# koi-gov
# KOI Governance & Naming Conventions

**Repository Status:** Active Development
**Lead Maintainer:** Gregory Landua
**Last Updated:** 2026-04-21 (v1.2.0)

---

## 🌱 Overview

Welcome to the **KOI (Knowledge Organization Infrastructure) Governance Repository**. This space holds the canonical semantic naming conventions and governance documents stewarded by Regen Network Development, PBC.

KOI is our collective infrastructure for creating coherent, transparent, and actionable knowledge objects within Regen Network. By maintaining semantic clarity, we enable decentralized teams, AI agents, and community participants to collaborate meaningfully.

---

## 📌 Key Documents

| Document | Purpose |
|----------|---------|
| [`KOI.regen-naming-convention-manifesto.v1.2.0.md`](./KOI.regen-naming-convention-manifesto.v1.2.0.md) | **Current manifesto.** Defines the KOI semantic naming schema, versioning practices, object types, ledger anchoring discipline, and governance process. |
| [`examples/`](./examples/) | Worked examples of each object type (v1.2.0 pilot set + more). |
| [`CONTRIBUTING.md`](./CONTRIBUTING.md) | Explains how to propose, pilot, and ratify changes to the KOI naming schema. |
| [`changelog.md`](./changelog.md) | Tracks all approved changes and updates to the naming conventions. |
| [`KOI.regen-naming-convention-manifesto.v1.1.0.md`](./KOI.regen-naming-convention-manifesto.v1.1.0.md) | Previous version (archived). |

---

## 📚 Repository Structure

```
koi-gov/
│
├── README.md                                              # You are here
├── KOI.regen-naming-convention-manifesto.v1.2.0.md        # Current manifesto
├── KOI.regen-naming-convention-manifesto.v1.1.0.md        # Previous version (archived)
├── KOI.regen-naming-convention-manifesto.v1.0.0.md        # Initial version (archived)
├── CONTRIBUTING.md                                        # Contribution guidelines
├── changelog.md                                           # Record of changes
├── examples/                                              # Worked examples of each type
│   ├── README.md
│   ├── core.spec.regen-os-learning-subroutines.v0.1.0.example.md
│   ├── core.plan.regen-os-phase-delivery.v0.1.0.example.md
│   ├── core.overview.regen-os-current-state.v0.1.0.example.md
│   └── core.registry.regen-os-artifact-registry.v0.1.0.example.md
├── docs/
│   └── semantic-naming-properties.md                      # Tool-by-tool implementation
└── LICENSE                                                # MIT License
```

---

## 🚀 How to Contribute

We enthusiastically welcome contributions from everyone! Here's how you can help:

- **Review the KOI Manifesto**: Familiarize yourself with the current naming conventions.
- **Open an Issue**: Suggest new prefixes, types, or relevance tiers.
- **Create a Pull Request**: Propose changes formally with your semantic reasoning and pilots.
- **Participate in Governance Discussions**: Join our regular calls or async forums to discuss proposals and feedback.

See [CONTRIBUTING.md](./CONTRIBUTING.md) for detailed instructions.

---

## 📖 Semantic Naming Quick Reference

### Naming Structure

```
[relevance].[type].[subject].vX.Y.Z
```

### Relevance Levels

- **`core`**: Fundamental, actively used, essential to strategic decisions.
- **`relevant`**: Informative, actively cited, influential in ongoing work.
- **`background`**: Contextual, supportive, historical, or ambient reference.

### Object Types

| Type | Description |
|------|-------------|
| `memo` | Structured strategic or operational documents. |
| `analysis` | Data-driven or qualitative deep dives. |
| `notes` | Informal or exploratory ideas and documentation. |
| `decision` | Official organizational decisions. |
| `readme` | Canonical documentation for directories or patterns. |
| `strategy` | Forward-looking strategic frameworks or business models. |
| `docs` | Reference documentation, specifications, or guides. |
| `feedback` | Structured feedback on proposals, products, or processes. |
| `research` | Investigative or exploratory research output. |
| `press` | External-facing communications and media materials. |
| `prompt` | AI prompt templates, agent configurations, or instruction sets. |
| `transcript` | Meeting or conversation transcripts, typically AI-generated. |
| `spec` *(v1.2.0)* | Technical specification, agentic loop spec, or agent instruction template. |
| `plan` *(v1.2.0)* | Phased execution plan with milestones, gates, and resource requirements. |
| `overview` *(v1.2.0)* | Canonical explainer of a system or domain at a point in time. |
| `registry` *(v1.2.0)* | Meta-document that indexes or directories other knowledge objects. |

### Semantic Versioning

- `vX.0.0`: Major conceptual shifts
- `vX.Y.0`: Minor, meaningful content updates
- `vX.Y.Z`: Editorial, non-conceptual adjustments or clarifications

---

## 🌿 Why KOI Matters

Implementing clear, semantic naming isn't trivial—it's foundational. It:

- Facilitates trust and clarity within distributed teams and collaborators.
- Supports adaptive governance and decision-making.
- Empowers human-AI collaboration through semantic precision.

Let's tend our shared garden of knowledge and coherence together.

---

## 🙌 Contact

Questions? Reach out directly to Gregory or open an issue in this repository.

Thank you for nurturing our collective coherence and stewardship!
