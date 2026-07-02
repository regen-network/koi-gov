# Canonical Vertical List (v1)

**Status:** Ratified vocabulary (proposed for merge with manifesto v1.3.0)
**Applies to:** KOI Repo `Vertical`, BizDev pipeline `Vertical`, and any published record's market-context tag
**Casing:** Title Case (no ALL CAPS, no lowercase)

The **Vertical** property tracks *market context* — the market or program space an object relates to. It is not an actor type and not an instrument type. This list replaces two divergent option sets (the legacy KOI 8-option ALL-CAPS list and the BizDev 10-option mixed-case list) with one shared 9-item vocabulary.

---

## Canonical values (v1)

| # | Canonical Name | Definition |
|---|---|---|
| 1 | **Insetting & Sustainable Supply Chain** | Corporate value-chain decarbonization and supply-chain integrity programs. |
| 2 | **Water Positive** | Water stewardship accounting, net-positive water commitments, water-risk programs. |
| 3 | **Eco Credits** | Full class of ecological credit instruments where buyers purchase units of ecological impact, outcomes, or actions — covers carbon, biodiversity, water, and stewardship credits. |
| 4 | **Non-Carbon Compliance Markets** | Regulatory-mandated markets for non-carbon environmental compliance (water quality, nutrients, wetlands, etc.). |
| 5 | **Nature & Biodiversity Finance** | Nature-related financial disclosure, biodiversity net-gain markets, TNFD-linked instruments. |
| 6 | **Impact Financing** | Broad category: blended finance, impact investing, concessional capital, first-loss tranches — not debt-instrument-specific. |
| 7 | **Green Bonds** | Debt-based financial instrumentation: green bonds, sustainability-linked bonds, labeled bond markets. |
| 8 | **Reporting** | Ecological and sustainability reporting standards (ESG, SDG, TNFD, SBTN, etc.) — claims that do not necessarily reach financial-grade verification; distinct from payment and credit systems. |
| 9 | **Grant Programs & Certifications** | Non-market funding mechanisms: grants, philanthropic programs, ecolabels, standards certifications. |

### Key conceptual distinctions

- **Eco Credits vs financial instruments.** Eco Credits are the underlying ecological asset (units of impact). Green Bonds and Impact Financing are vehicles that monetize, bundle, or reference those units. Different layers — Vertical tracks market context, not instrument type.
- **Impact Financing vs Green Bonds.** Impact Financing is broad (equity, quasi-equity, blended, concessional). Green Bonds are specifically debt-based. Distinct because the financing mechanism differs materially.
- **Reporting vs crediting.** Reporting standards (ESG, TNFD, SDG) operate at a different claims-maturity level than eco-credit or compliance markets and need not reach financial-grade verification. This distinction is load-bearing for how Regen positions its verification infrastructure.

---

## Retirements

| Retired option | Was in | Reason |
|---|---|---|
| `PUBLIC SECTOR` | KOI Vertical | Actor-type axis bleeding into Vertical. Retire here; lives on the Organizations DB as **Actor Type**. |
| `General Tech Provider` | BizDev Vertical | Not a market vertical — an actor type / service offering. Retire from Vertical. |

---

## Historical alias map (for backfill)

Legacy values remain valid during migration; sensors and new objects use canonical names going forward. Mapping for automated normalization:

```
INSETTING                                            → Insetting & Sustainable Supply Chain
WATER POSITIVE                                       → Water Positive
Water Positive Accounting                            → Water Positive
CARBON CREDITS                                       → Eco Credits
ECOCREDITS                                           → Eco Credits
Eco Credit Market                                    → Eco Credits
IMPACT FINANCING                                     → Impact Financing
SDG REPORTING                                        → Reporting
regulated markets                                    → Non-Carbon Compliance Markets
Environmental Regulation and Compliance (non carbon) → Non-Carbon Compliance Markets
Non-Carbon Compliance Markets                        → Non-Carbon Compliance Markets (no change)
Nature Related Financial & ESG                       → Nature & Biodiversity Finance
Biodiversity Market                                  → Nature & Biodiversity Finance
Bond Markets                                         → Green Bonds
Grant Programs & Certifications                      → Grant Programs & Certifications (no change)
PUBLIC SECTOR                                        → [retire — remap to Actor Type on Organizations DB]
General Tech Provider                                → [retire — remap to Actor Type on Organizations DB]
```

---

## Migration procedure (surface-agnostic)

1. Add the 9 canonical values to each `Vertical` field (KOI Repo, BizDev), keeping legacy values present as aliases.
2. Backfill existing rows via the alias map above (scripted where possible; by attrition otherwise).
3. Once no rows reference a legacy value, remove the legacy option.
4. `PUBLIC SECTOR` and `General Tech Provider` rows are remapped to **Actor Type** on the Organizations DB, not to a Vertical.

Surface-specific execution (field IDs, DDL, sequencing) lives in the internal metadata-upgrade runbook, not in this public vocabulary doc.
