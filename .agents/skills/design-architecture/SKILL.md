---
name: design-architecture
description: "Draft or update portable architecture-design records for an SDLC initiative, covering system boundaries, security, integrations, deployment, and operations."
---

# Architecture design

Produce or update `design/architecture-design.md` for the active initiative. Establish reviewable boundaries and operational consequences without turning an approved approach into approval of precise technologies or mechanisms.

Read relevant phase `questions.md` entries before drafting. Use [resolve-questions](../resolve-questions/SKILL.md) to record newly raised questions and unconfirmed assumptions, link their owning entries from this record, and reconcile answers through the concerned skills. The shared contract governs timestamps, raising/concerned skills, options, response history, and reconciliation status.

## Start with project evidence

Read [the shared document contract](references/document-contract.md) on **every invocation**, then read the PRD, requirements decisions, design decisions, domain model, UX design, and existing technical constraints. Resolve the initiative and preserve established equivalent records.

Use [the architecture template](assets/architecture-design-template.md). Retain useful project-specific detail. Within delegated design scope, propose or recommend technologies, vendors, runtime patterns, and operational targets when they resolve a real design question; give rationale, alternatives or decision criteria where material, and an explicit `Proposed` status. Treat existing constraints and decisions as binding. An approved product behavior or architecture direction does not approve a particular library, provider, protocol, or topology.

## Design the system boundaries

- Begin with a `Layer | Choice | Status and reference` table. State each component's responsibility and whether the choice is confirmed, proposed, constrained, or pending. Link evidence for confirmed choices.
- Add a Mermaid boundary diagram showing people or clients, system-owned components, stores, external systems, and important trust/data flows. Keep it conceptual enough to remain useful before implementation.
- Explain authentication, authorization, secrets/session boundaries, data isolation, and audit requirements that derive from scope. Mark security review or a spike where the mechanism remains open.
- Describe persistence and isolation boundaries, file/object ownership and lifecycle where relevant, integration ownership/failure behavior, and which functional boundaries are synchronous, asynchronous, or unresolved.
- Cover deployment and operations in proportion to risk: environments, configuration/secrets, migrations, backups/recovery, observability, alerting, support/fallback, performance/availability assumptions, and rollback. Do not invent service levels, providers, retention periods, or monitoring results.
- Identify validation and handoff work before build, including spikes, security/design review, API/database alignment, migration rehearsal, and operational runbook needs.

## Finish well

Separate approved constraints from hypotheses and preserve authority for each. Link dependencies and decisions with relative links, name risks and next actions, and verify diagram/table narrative agrees with API/database records without choosing implementation internals by implication.

After completing this design or a material revision, use the [optional independent design-review workflow](../sdlc/SKILL.md#offer-independent-design-review) to link the result, name the next lifecycle step, and offer a subagent review/stress test before normal approval.
