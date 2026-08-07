# Schema Governance Boundary (v1)

**Status:** Proposed — pending governance-call ratification (stacks with manifesto v1.2.0 / v1.3.0)
**Applies to:** `regen-network/koi-gov` and `regen-network/regen-data-standards`
**Canonical home:** this file. `regen-data-standards` points here; it does not restate the contract.

Regen governs **two adjacent and interdependent schema sets**. This document declares which repository has authority over which, how the two reference each other, and what happens at the seam.

The seam is not new. Both repositories already reach for each other — `Claim.supersedes` accepts ORN RIDs, `Attestation.hasReviewer` requires "a registered identity (KOI entity URI and/or wallet address)", and koi-gov v1.3.0 defines exactly that identifier. This document makes the existing connection explicit and governed.

---

## The two domains

| | **Registry system** | **Non-registry operational + knowledge** |
|---|---|---|
| **Authority** | [`regen-data-standards`](https://github.com/regen-network/regen-data-standards) | `koi-gov` (this repo) |
| **Namespace** | `https://framework.regen.network/schema/` (prefix `rfs:`) — dereferenceable | `orn:regen.<entity-class>:<context>/<reference>` |
| **Form** | LinkML sources → RDF / JSON-LD / TTL | Markdown manifesto + controlled vocabularies |
| **Covers** | Projects, credit classes, methodologies, crediting programs, registries, credit protocols, claims, attestations, impacts, SDGs, geometry, taxonomies | RegenOS, Compass, work coordination, knowledge objects, decisions, specs, memos, analyses, registries-of-artifacts |
| **Governs** | Structure and semantics of registry data | Naming, Relevance, Type, Vertical, Access tier, Publication decision, RID identity, ledger-anchoring discipline |

**One-line test:** *does the schema describe an object the ecocredit registry issues, holds, or verifies?* If yes, `regen-data-standards`. If it describes how Regen itself works, decides, or publishes, `koi-gov`.

---

## Rules

**SGB-1 — Domain assignment.** Every schema has exactly one governing repository, assigned by the test above. Ambiguity resolves toward `regen-data-standards` when the object is registry-facing, toward `koi-gov` when it is organization-facing.

**SGB-2 — No cross-domain redefinition.** Neither repository redefines a class the other owns. koi-gov does not define `Claim`; `regen-data-standards` does not define Access tiers. Where a domain needs the other's concept, it **references** it.

**SGB-3 — Reference by identifier, across a shared RID space.** Registry-domain objects are referenced by IRI under `rfs:`. Non-registry objects are referenced by ORN under `orn:regen.*`. Both are valid RIDs under RID v3, which spans URI schemes (`http`, `https`) and ORNs alike. **No translation layer is required — the RID space is the join.** A slot that may hold either declares `range: uriorcurie`.

**SGB-4 — Cross-cutting properties are koi-gov's, in both domains.** Access tier, Publication target, RID identity, and ledger-anchoring discipline are organization-wide governance concerns. They apply to registry artifacts too — a credit-class schema published to an external surface is a Publication decision under manifesto §Publication (P1: publish-by-decision, not by default), regardless of which repo defines its structure. `regen-data-standards` does not restate these rules; it inherits them.

**SGB-5 — One anchoring mechanism.** Both domains anchor through Regen Ledger `x/data` `MsgAnchor`. `Claim.contentHash` (BLAKE2b-256) + `Claim.dataIri` are the registry-domain expression of the same mechanism the manifesto §Ledger Anchoring describes for KOI objects. The canonical/manifest/receipt triad and the rename discipline apply to both.

**SGB-6 — Change coordination at the seam.** A change to any slot that carries a cross-domain reference (see the inventory below) requires notice to the other repository before merge. Adding a new cross-domain reference requires adding it to that inventory.

**SGB-7 — The `orn:regen.*` namespace is governed here.** Its grammar is manifesto §RID. Entity-classes are enumerated in this repository. Any implementation minting `orn:regen.*` identifiers — including the [`regen-koi-mcp`](https://www.npmjs.com/package/regen-koi-mcp) client and Regen's internal knowledge-base tooling — conforms to that grammar or is non-conformant.

---

## Cross-domain reference inventory

Existing seam points, as of 2026-08-07. Changes to these are SGB-6 events.

| Slot | Repo | Range | Points at |
|---|---|---|---|
| `Claim.supersedes` | data-standards | `uriorcurie` — *"Accepts full IRIs and CURIE-form identifiers such as ORN RIDs (orn:...)"* | either domain |
| `Attestation.attestsClaim` | data-standards | *"by RID or IRI"* | either domain |
| `Attestation.hasReviewer` | data-standards | `Entity` — *"Must have a registered identity (KOI entity URI and/or wallet address)"* | `orn:regen.entity:org/<slug>` |
| `Claim.dataIri` | data-standards | `uri` — Regen Data Module IRI from content hash | on-chain anchor (shared, SGB-5) |
| RID property | koi-gov | `orn:regen.<entity-class>:<context>/<reference>` | may reference `rfs:` classes |

---

## Open items

1. **Enumerate the `orn:regen.*` entity-classes.** The manifesto gives the grammar and three examples (`document`, `artifact`, `entity`). The [`regen-koi-mcp`](https://www.npmjs.com/package/regen-koi-mcp) client independently carries six (`document`, `ontology`, `methodology`, `credit`, `agent`, `project`). Two of those — `methodology` and `project` — name **registry-domain** objects, which under SGB-1/SGB-2 are `rfs:` classes and should be referenced by IRI rather than ORN-minted. Ratify the canonical entity-class list and align implementations to it.
2. **Decide whether `rfs:` classes get ORN aliases.** SGB-3 says they do not need them. Confirming this closes the question for implementers.
3. **Upstream registration.** `orn:regen.*` is not yet registered in [`DynamicalSystemsGroup/rid-registry`](https://github.com/DynamicalSystemsGroup/rid-registry), the ORN type registry for KOI-net, whose README describes itself as coordinating RID types rather than authoritatively defining them. Once items 1–2 are ratified, register the namespace there with a pointer to this document — and offer the governance model itself (access tiers, publication-by-decision, RID-as-identity, anchoring) as a contribution to that coordination effort, should it be useful.

## Related

- `KOI.regen-naming-convention-manifesto.v1.3.0.md` — §RID, §Publication, §Ledger Anchoring, §Access
- `docs/vertical-canonical-v1.md` — the Vertical controlled vocabulary (shared with the BizDev pipeline)
- `regen-data-standards/schema/README.md` — LinkML sources and generation
- `regen-data-standards/schema/GOVERNANCE.md` — the reciprocal pointer to this document
