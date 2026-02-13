# Contributing to KOI Governance

Thank you for your interest in contributing to the **Knowledge Organization Infrastructure (KOI)**! This document outlines how you can meaningfully contribute to KOI governance, naming conventions, and semantic standards.

---
👐 Who Can Contribute?

Anyone! You don’t need to be a developer or GitHub expert. If you’re creating meaningful documents—like a plan, decision, proposal, or dataset—you can contribute to KOI.

This includes scientists, policy designers, technologists, and community leaders.

## 👐 How to Contribute

We warmly invite all community members, non-technical participants, and Regen Network stakeholders to contribute through the following methods:

1. **Propose changes** via GitHub Pull Requests (PRs).
2. **Join weekly governance calls** to discuss, review, and refine proposals.
3. **Participate in piloting and testing** new naming conventions internally before official adoption.

---

## 📌 Proposing Changes

To propose a new KOI prefix, type, relevance tier, or naming convention:

1. **Create a clearly named proposal document** using the current KOI naming standard:
    ```
    meta.reflection.koi-[proposed-change-name].v0.1.0.md
    ```

2. **Clearly articulate your proposal** within the document, including:
    - The specific prefix, type, or tier proposed.
    - Semantic gaps or ambiguities it resolves.
    - Examples demonstrating how the new proposal would be used.
    - Any anticipated tradeoffs (e.g., complexity, readability, tooling impact).

3. **Submit your proposal as a Pull Request (PR)** to this repository.
    - Clearly summarize your changes and reasoning in the PR description.
    - Indicate whether your change is major, minor, or patch according to semantic versioning guidelines.
  
   > 🔍 Tip: When piloting new KOI objects in Notion or similar tools, consider separating the full KOI name into structured properties. This supports better searchability, clarity, and integration with AI tools and metadata crawlers.

---

## 🚧 Piloting & Testing Proposals

Before official adoption, each new KOI naming convention proposal should undergo a short piloting phase:

- **Internal Piloting:**
    - Use your proposed naming convention in a limited, clearly defined set of internal documents.
    - Gather feedback on clarity, usability, and semantic coherence.

- **Document Results:**
    - Update your PR or proposal document with pilot findings.
    - Clearly indicate whether the pilot supported adopting the proposal as-is or if modifications are needed.

---

## 📆 Governance & Review Process

All proposals are reviewed and ratified through our weekly governance meetings, held jointly by Regen Network Development and Regen Foundation teams:

- **Weekly Governance Calls:**
    - Time-boxed, efficient review and discussion.
    - Opportunity to present, discuss, and refine proposals in real-time.

- **Decision-making:**
    - Consensus-driven, with clear documentation of any objections or amendments.

- **Ratification & Merge:**
    - Approved proposals are merged into the repository, with explicit semantic version updates.
    - Changes and rationales are logged in the [`changelog.md`](./changelog.md).

---

## 📖 Semantic Versioning Discipline

Clearly communicate the impact of your proposal using semantic versioning in your PR:

- `vX.0.0`: Major conceptual shifts (introducing entirely new prefixes, tiers, or fundamental restructuring)
- `vX.Y.0`: Meaningful updates or expansions of existing conventions
- `vX.Y.Z`: Editorial, non-conceptual clarifications, or minor refinements
-  You may also specify whether the KOI object uses `single-string` or `property-based` naming in your PR.


Include clear explanations of your semantic versioning choices in your PR description.

## 📝 Format Declaration Tip

When submitting a new KOI object or naming schema, please specify whether you're using:

- a **single-string format**  
  (e.g., `core.memo.token-strategy.v1.0.0` as the title), or  
- a **property-based format**  
  (e.g., a clean human-readable title plus metadata fields like `KOI Name`, `Type`, `Version`, etc., in Notion, YAML, or JSON).

This helps reviewers understand the intended usage context and ensures consistency across different tools and agents in the KOI ecosystem.

---

## ❓ Issues & Community Feedback

- Open an **Issue** on GitHub to:
    - Suggest ideas without submitting a formal proposal.
    - Provide general feedback, ask questions, or clarify existing naming conventions.

- Issues will be reviewed and addressed during weekly governance calls.

---

## 🙌 Getting Support

For assistance, questions, or guidance, please:

- Reach out directly to Gregory Landua or designated maintainers.
- Attend the weekly governance calls.
- Open an issue clearly labeled as `question` or `support`.

---

Thank you for contributing to the clarity, coherence, and collective wisdom of KOI Governance!

