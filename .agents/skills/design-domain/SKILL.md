---
name: design-domain
description: "Draft or update a portable domain-model design record for an SDLC initiative. Use for concepts, relationships, ownership, lifecycles, and business invariants; do not use it to specify a physical database schema."
---

# Domain model

Produce or update `design/domain-model.md` for the active initiative. This record makes the business model reviewable before implementation; it is not a database design or an implicit approval of a storage mechanism.

Read relevant phase `questions.md` entries before drafting. Use [resolve-questions](../resolve-questions/SKILL.md) to record newly raised questions and unconfirmed assumptions, link their owning entries from this record, and reconcile answers through the concerned skills. The shared contract governs timestamps, raising/concerned skills, options, response history, and reconciliation status.

## Start with project evidence

Read [the shared document contract](references/document-contract.md) on **every invocation**, then read the initiative's PRD, requirements decisions, design decisions, and dependent design records that exist. Resolve the initiative and established equivalent paths before writing. Preserve useful existing content and conventions.

Use [the domain-model template](assets/domain-model-template.md) as the information contract. Adapt headings and tables to the project's scale; do not omit an applicable concern simply because a project has no settled answer. Mark it `Proposed`, `Pending review`, `Unknown`, or `Not applicable — <reason>` rather than inventing a decision.

## Model the domain

- Define stable business concepts, their owner, and their relationships in a Mermaid conceptual relationship diagram. Use project-specific names; include cardinality where it clarifies ownership or participation. Do not present table names, columns, foreign keys, index choices, or implementation classes as concepts unless that is actual business language.
- Follow the diagram with the required `Concept | Meaning and owner | Key relationships and rules` table. Give each important concept one place to explain purpose, accountable owner, boundaries, and governing rules.
- State ownership, access, and isolation boundaries. Explain who may act on or view sensitive concepts, but defer transport-specific authorization details to API and architecture design.
- Describe meaningful lifecycles and invariants as observable rules: allowed states/transitions, history that must survive change, uniqueness, deletion/archive behavior, time semantics, and cross-concept rules. Use a numbered sequence where a lifecycle has ordered transitions.
- Define integrity and transaction boundaries at the business level: which changes must succeed together or not at all, and which concurrent changes need a defined outcome. Do not select locks, tables, or transaction primitives unless approved.
- Link relevant approved requirements and decisions by ID with relative Markdown links. Cite a decision only for what it decides; distinguish confirmed behavior from an implementer proposal.

## Finish well

Add focused remaining-review questions for unresolved rules, risky assumptions, data ownership, lifecycle edge cases, and transaction boundaries. Reconcile dependent records when authorized, or report the affected record and needed follow-up. Confirm the diagram, table, status, dates, authority, and links are consistent.

After completing this design or a material revision, use the [optional independent design-review workflow](../sdlc/SKILL.md#offer-independent-design-review) to link the result, name the next lifecycle step, and offer a subagent review/stress test before normal approval.
