# Semantic Naming via Properties

KOI objects can now use **structured properties** (instead of embedding everything in the title) when tools support them. This enables both **human usability** and **machine interoperability**.

---

## 🧠 Why Properties Matter

- Clear display titles help humans scan content.
- Structured metadata fields enable search, sorting, and semantic indexing.
- Prepares KOI for integration with agents, APIs, and graph-based storage systems.

---

## 🛠 Tool-by-Tool Implementation

### 🟡 Notion

Use a Notion Database to represent KOI Objects with structured properties:

| Property    | Value                                                  |
|-------------|--------------------------------------------------------|
| Title       | RegenOS Overview — Unified Operating System for RND PBC |
| KOI Name    | core.strategy.regen-os-overview.v0.1.0                 |
| Relevance   | core                                                   |
| Type        | strategy                                               |
| Subject     | regen-os-overview                                      |
| Version     | v0.1.0                                                 |
| Status      | draft                                                  |
| Access      | Internal                                               |
| Ready for AI| yes                                                    |

- **Search Tips**: Notion prioritizes title search. Use filters to query metadata.
- **Linking**: Canonical versions can link to Google Docs, GitHub, or exported JSON.

---

### 🔵 Google Docs

- Use full KOI name in **title** or include a metadata table at the top of the document.

Example metadata block:
```
Title: RegenOS Overview — Unified Operating System for RND PBC
KOI Name: core.strategy.regen-os-overview.v0.1.0
Relevance: core
Type: strategy
Subject: regen-os-overview
Version: v0.1.0
Status: draft
Access: Internal
```

---

### ⚪ GitHub

- Use KOI naming in file and folder names.
- Add metadata in frontmatter (for markdown files):

```yaml
---
koi_name: core.strategy.regen-os-overview.v0.1.0
relevance: core
type: strategy
subject: regen-os-overview
version: v0.1.0
status: draft
access: Internal
ready_for_ai: true
---
```

---

## 🔍 Search & Retrieval Considerations

| Tool        | Indexed Fields            | Best Practice                                     |
|-------------|---------------------------|---------------------------------------------------|
| Notion      | Title + properties        | Use filters for semantic queries                  |
| GDocs       | Title + body              | Put KOI metadata near the top                     |
| GitHub      | File/Folder + frontmatter | Embed metadata in filenames and YAML blocks       |

---

## 🌱 Looking Ahead

These property-based formats prepare KOI for:
- JSON-LD / RDF export
- AI-assisted retrieval
- Multi-agent coordination systems

We name to create clarity. Structured properties help us grow semantic legibility for both humans and machines.

