# KOI Examples

This directory contains **worked examples** of KOI objects following the canonical naming convention. Each example is a realistic minimal artifact demonstrating one of the object types defined in the manifesto.

## v1.2.0 Pilot Set (RegenOS)

The four examples below satisfy the CONTRIBUTING.md minimum-3-object pilot requirement for v1.2.0's new object types. Each is grounded in a concrete RegenOS Phase 0 artifact (2026-04-21 builders-standup prep session).

| File | Type | Pilot for |
|---|---|---|
| [`core.spec.regen-os-learning-subroutines.v0.1.0.example.md`](./core.spec.regen-os-learning-subroutines.v0.1.0.example.md) | `spec` | Agent-loop and pattern specifications |
| [`core.plan.regen-os-phase-delivery.v0.1.0.example.md`](./core.plan.regen-os-phase-delivery.v0.1.0.example.md) | `plan` | Phased execution plans |
| [`core.overview.regen-os-current-state.v0.1.0.example.md`](./core.overview.regen-os-current-state.v0.1.0.example.md) | `overview` | Canonical system explainers |
| [`core.registry.regen-os-artifact-registry.v0.1.0.example.md`](./core.registry.regen-os-artifact-registry.v0.1.0.example.md) | `registry` | Artifact / URL / RID directories |

## How to Read These Examples

Each example file:

- Uses the canonical KOI Name as its filename: `[relevance].[type].[subject].vX.Y.Z.example.md`
- Includes YAML frontmatter with the full property set (KOI Name, Type, Relevance, Version, Status, Access, Ready for AI)
- Has a body that exemplifies the type's structural conventions (e.g., specs have inputs/outputs/loop; registries have tabular indexes)
- Ends with a note about pilot evidence and revision trigger

## Adding New Examples

When proposing a new object type, version bump, or convention change, include at least 3 pilot examples in this directory following the naming convention above. See [CONTRIBUTING.md](../CONTRIBUTING.md) for the full proposal → pilot → review → ratify process.
