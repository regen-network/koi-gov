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
| Title       | Q2 Sprint Strategy – Regen Commons                     |
| KOI Name    | core.objective.rnd-foundation-sprint.v2025-Q2.v0.1.4  |
| Type        | core.objective                                         |
| Relevance   | core                                                   |
| Version     | v2025-Q2.v0.1.4                                        |
| Status      | active                                                 |

- **Search Tips**: Notion prioritizes title search. Use filters to query metadata.
- **Linking**: Canonical versions can link to Google Docs, GitHub, or exported JSON.

---

### 🔵 Google Docs

- Use full KOI name in **title** or include a metadata table at the top of the document.

Example metadata block:
```
Title: Q2 Sprint Strategy – Regen Commons
KOI Name: core.objective.rnd-foundation-sprint.v2025-Q2.v0.1.4
Version: v2025-Q2.v0.1.4
Type: core.objective
Relevance: core
Status: active
```

---

### ⚪ GitHub

- Use KOI naming in file and folder names.
- Add metadata in frontmatter (for markdown files):

```yaml
---
koi_name: core.objective.rnd-foundation-sprint.v2025-Q2.v0.1.4
version: v2025-Q2.v0.1.4
type: core.objective
relevance: core
status: active
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

