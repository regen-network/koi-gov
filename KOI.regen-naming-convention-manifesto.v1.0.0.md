# **KOI Naming Convention Manifesto**

**Document ID:** `KOI.naming-convention-manifesto.v1.0.0` **Maintained by:** RND PBC **Last Updated:** April 7, 2025

## **Preface: Why This Document Uses the `KOI.` Namespace**

This document is named using the `KOI.` prefix because it defines the **governance structure of KOI itself**. Unlike topical documents labeled `core.`, `relevant.`, or `background.`, this document **sets the naming rules and conventions** for all other KOI entries.

Using `KOI.` as a root-level namespace signals:

* This is a **cross-cutting specification** that applies to *all workstreams* (token strategy, commons, ledger, etc.)  
* It defines **meta-protocols** like naming, versioning, and document lifecycle handling  
* It exists **outside and above** topical folders, acting as a shared standard for semantic clarity

Decision: All future canonical documents governing KOI schema and infrastructure will use the `KOI.` namespace, not `core.`, to distinguish system-level protocols from content-specific instances.

For example:

```
KOI.versioning-guide.v1.0.0
KOI.semantic-index-proposal.v0.3.0
KOI.naming-convention-manifesto.v1.0.0
```

This distinction preserves both **semantic legibility** and **tooling compatibility**, ensuring that humans and machines can correctly interpret the role of KOI documents within a growing decentralized knowledge infrastructure.

---

## **Purpose**

This document defines the semantic naming convention used across the KOI (Knowledge Organization Infrastructure) system stewarded by Regen Network Development, PBC. It articulates the reasons for using this naming convention, the structure itself, the upgrade process, and principles to guide when and how to expand the namespace. The intention is to foster collective coherence, support semantically legible digital institutions, and align naming practices with Regen’s deep commitments to regeneration, trust, and clarity.

---

## **Audience**

This guide is for anyone contributing knowledge to Regen Network — whether you're a scientist, organizer, developer, or policy thinker. You don’t need to be technical to use this guide. You just need to care about naming things clearly so others can find and reuse them.


## **Current Structure**

The current KOI naming system follows this schema:

```
[relevance].[type].[subject].vX.Y.Z
```

### **1\. Relevance Tier (prefix)**

| Prefix | Meaning |
| ----- | ----- |
| `core.` | Canonical source of truth. Approved, operational, or final for reference. |
| `relevant.` | Informative, influential, cited actively in other work. |
| `background.` | Contextual, ambient, inspirational. Not directly cited but informs direction. |

### **2\. Object Type**

| Type | Meaning |
| ----- | ----- |
| `memo` | Strategic thought piece, potentially evolving into `core` guidance. |
| `analysis` | Quantitative or qualitative breakdown of relevant data. |
| `notes` | Raw or lightly structured ideas, early-stage ideation. |
| `readme` | Canonical documentation of a pattern or directory. |
| `decision` | Snapshot of an agreed-upon organizational decision. (Proposed extension) |

### **3\. Subject Field**

* Freeform, hyphen-separated, ideally scoped to topic (e.g., `regen-token-flywheel`, `commons-inquiry`, `dau-comparison`)

### **4\. Versioning**

* Semantic versioning format: `vX.Y.Z`

  * `X` \= major conceptual shift

  * `Y` \= minor revision

  * `Z` \= editorial or structural update only

---
## 🧠 Alternate Format: Semantic Properties

In addition to embedding KOI metadata into a single string (e.g., `core.memo.q2-sprint-strategy.v1.0.0`), KOI objects can use **distributed properties** in tools that support it (like Notion, YAML frontmatter, or JSON).

### Example in Notion:

| Property    | Value                                                  |
|-------------|--------------------------------------------------------|
| KOI Name    | `core.objective.q2-commons-activation.v2025-Q2.v1.0.0` |
| Type        | `core.objective`                                       |
| Relevance   | `core`                                                 |
| Version     | `v2025-Q2.v1.0.0`                                       |
| Status      | `active`                                               |

**Benefits:**
- Machine-readability for AI agents and future KOI indexers
- Human usability via clear titles
- Structured search, sorting, and linking across platforms

➡ See: [`docs/semantic-naming-properties.md`](./docs/semantic-naming-properties.md)

## **Rationale: Why This Naming Convention Exists**

### **1\. Legibility for Distributed Teams**

Names act as a shared interface for collective work. Just as ecosystems rely on keystone species to stabilize complexity, **humans require shared semantic anchors** in order to govern, evolve, and trust decentralized infrastructures.

In alignment with Regen's Corporate Direction framework, naming conventions are a mechanism for cultivating *Harmonized Agency* and *Nest Caring* in how we manage complexity together.

### **2\. Support Transparent, Trustworthy Infrastructure**

Just as our `Ecocredit Process Heptad` formalizes how ecological assets come into being, KOI naming formalizes the emergence of *knowledge assets*—from raw insights to policy decisions. It allows:

* Tools to reliably parse relevance

* Humans to make fast judgments about which documents to trust

* Auditable, upgradeable knowledge systems to form organically

### **3\. AI-Native Semantic Graphs**

To realize the vision of **Regen AI Enneagram (IS/AS)** and machine-facilitated regenerative institutions, naming conventions must be both **machine-readable and human-meaningful**. The KOI prefix system helps AI agents:

* Filter and reason over source material

* Summarize and synthesize accurately

* Respect epistemic boundaries (e.g., core vs speculation)

---

## **Process for Upgrading the KOI Naming Convention**

When considering changes to this schema:

### **1\. Propose**

Create a memo using the current naming structure. e.g.,

```
meta.reflection.koi-schema-expansion.v0.1.0
```

Include:

* The new prefix/type proposed

* The rationale (new use case, lifecycle distinction, clarity gain)

* Tradeoffs (complexity, ambiguity, overhead)

### **2\. Pilot**

Use the proposed prefix or structure in a limited context for 1–2 weeks. Track whether it adds clarity or confusion.

### **3\. Review & Ratify**

Present findings during a team session (retreat, KOI sync, etc). If consensus agrees, upgrade the KOI readme version and apply to future work.

---

## **When to Expand the Namespace**

You **may want to add a new prefix or type** if:

* The lifecycle stage of the object is unclear (e.g., is this active testing or a legacy memo?)

* You find multiple documents are blurring the meaning of existing tiers

* You want to create a `decision log`, `experimental module`, or `archived work` and it doesn’t clearly fit `core`, `relevant`, or `background`

## 🔍 Examples for Non-Coders

| Human-Friendly Title             | KOI Name                                               |
|----------------------------------|--------------------------------------------------------|
| Earth Stewardship Q2 Plan        | `core.plan.earth-stewardship.v2025-Q2.v1.0.0`          |
| Biodiversity Credit Metrics (Draft) | `exploratory.notes.biodiversity-metrics.v0.2.1`     |


## **Closing Reflection**

In the spirit of *Regenerative Semantics*, naming is not trivial—it is a sacred act of **bringing coherence into a complex living system**. As our KOI grows more self-aware and integrated with machine agents and ecological flows, this naming convention will support:

* Adaptive governance

* Credible knowledge sharing

* Machine-human collaboration

To name is to tend the garden of meaning. We name not just to label, but to **create the conditions for trust, transparency, and thrivability**.

---

## **Draft KOI Naming Convention Changelog**

| Version | Date       | Change Summary                                                      | Author(s)           |
|---------|------------|----------------------------------------------------------------------|---------------------|
| 1.0.0   | 2025-04-07 | Initial release with core, relevant, background relevance tiers + vX.Y.Z system | RND PBC Retreat Team |
| 1.1.0   | 2025-04-16 | Added property-based format guidance (Notion, GDocs, GitHub)         | Regen Coordination  |

