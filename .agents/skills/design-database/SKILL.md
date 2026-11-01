---
name: design-database
description: "Design or update an initiative's database record, schema dictionary, and ERD when data relationships, integrity, migration, or concurrency need explicit treatment."
---

# Database design

Create or update a portable, build-ready database design that expresses the approved product model without inventing a stack or copying rules from another initiative.

Read relevant phase `questions.md` entries before drafting. Use [resolve-questions](../resolve-questions/SKILL.md) to record newly raised questions and unconfirmed assumptions, link their owning entries from this record, and reconcile answers through the concerned skills. The shared contract governs timestamps, raising/concerned skills, options, response history, and reconciliation status.

## Required context

At the start of every use, read [the shared SDLC document contract](references/document-contract.md). Then locate the project root and initiative, and read the relevant PRD, requirements decisions, design decisions, domain model, API design, existing database records, and delivery backlog when they exist. Read later decision amendments or supersession before treating an earlier decision as current.

Apply existing project conventions and explicit user instructions first. Do not assume a database engine, tenancy model, authentication approach, business terminology, retention policy, or deployment environment. Describe unresolved choices as proposals. Update the relevant phase decisions when the current task includes a new choice or proposal; existing authorization for document work covers directly related record maintenance. Do not create decisions for mere observations.

## Deliverables

Use the existing project path when present. Otherwise produce `docs/initiatives/<initiative>/design/database-design.md`.

For a substantial or implementation-ready model, also create or update these only when they improve clarity:

- `design/database-schema.md`: field-level dictionary.
- `design/database-erd-source.md`: editable Mermaid ERD source.
- `design/database-erd.md`: readable rendered/view document that links its source.
- `design/assets/`: rendered diagrams, only when a project-supported renderer exists or the user requests image assets.

Keep one source of truth for each detail. The design links the dictionary and ERD rather than duplicating every field. Preserve an established equivalent path and link it instead of creating a competing record.

For a substantive design, start from [the database design template](assets/database-design-template.md). When a field-level dictionary is warranted, use [the schema dictionary template](assets/database-schema-template.md). Copy and adapt the templates into the initiative; do not edit the skill assets.

## Database design content

Use a descriptive H1 plus explicit status and ISO update date. State which behaviours and choices are approved, proposed, pending review, or unknown. Cover, in proportion to the feature:

1. Relationship overview and conceptual data ownership. Include a Mermaid relationship diagram when relationships materially benefit from a visual.
2. Entity identity, primary keys, external/public identifiers, relationship cardinality, lifecycle/archival, and ownership or isolation boundaries where applicable.
3. Integrity rules: foreign keys, uniqueness, checks, deletion/archive rules, immutable history, derived views/projections, and where a rule is enforced.
4. Time semantics: authoritative clock, timezone/local-date representation where relevant, timestamps, versioning, effective dates, and whether values are derived or stored.
5. Access/isolation and sensitive-data treatment, only where the product needs them. Do not call every project multi-tenant.
6. Transactions, concurrency, retry/idempotency, lock or conflict behaviour for multi-record and high-contention operations. Align it with API commands and observable error/recovery behaviour.
7. Indexes guided by actual read/write paths, migrations/backfill/compatibility, retention/deletion/recovery, operational constraints, and outstanding technical review or spike work.

Separate the conceptual model (business meanings and invariants) from the physical proposal (tables, types, indexes, engine-specific mechanisms). Explain the relationship when a physical design encodes a business invariant. Keep names, relationship direction, optionality, keys, and constraints consistent across the narrative, dictionary, ERD, API design, and domain model. Reconcile affected documents when scope allows; otherwise report the conflict and needed follow-up.

## Schema dictionary and ERD rules

Document `?` immediately before or alongside the tables as the notation for nullable fields. Include shared fields or explicitly link to their definition so timestamp, version, audit, and time semantics remain clear. Specify every primary key, relevant foreign key, candidate/unique key, meaningful check, and index purpose; do not imply referential integrity from a diagram alone.

Keep Mermaid source editable and readable. Make the diagram a relationship map, not an attempt to squeeze every column into a single image. If several views are needed, say that repeated entities represent the same logical table/model. Do not copy a source project's renderer blindly: inspect its assumptions, dependencies, input format, output locations, and runtime. Add a renderer only if it is portable and worth maintaining; run it and verify its outputs if you add or change it. Otherwise keep Mermaid source and a Markdown view without fabricated image assets.

## Completion check

Before handoff, verify paths and relative links, status/authority labels, decision references, and agreement between the PRD/domain/API, dictionary, and ERD. Report the documents changed, approved versus pending choices, and the next technical or review action. Do not claim schema validation, migrations, performance, isolation, or concurrency testing occurred unless evidence exists.

After completing this design or a material revision, use the [optional independent design-review workflow](../sdlc/SKILL.md#offer-independent-design-review) to link the result, name the next lifecycle step, and offer a subagent review/stress test before normal approval.
