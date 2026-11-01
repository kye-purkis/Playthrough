---
name: design-api
description: "Draft or update portable API contract-design records for an SDLC initiative, covering resource identity, access, request/response behavior, errors, and consistency rules."
---

# API design

Produce or update `design/api-design.md` for the active initiative. Document a reviewable product/API contract without implementing software or claiming that an approved approach approves exact endpoint, protocol, schema, or concurrency mechanisms.

Read relevant phase `questions.md` entries before drafting. Use [resolve-questions](../resolve-questions/SKILL.md) to record newly raised questions and unconfirmed assumptions, link their owning entries from this record, and reconcile answers through the concerned skills. The shared contract governs timestamps, raising/concerned skills, options, response history, and reconciliation status.

## Start with project evidence

Read [the shared document contract](references/document-contract.md) on **every invocation**, then read the PRD, requirements and design decisions, domain model, UX design, architecture design, and database design when present. Resolve the initiative and preserve an established contract path or published API convention.

Use [the API-design template](assets/api-design-template.md). Match an existing project convention where it exists; otherwise make format choices explicitly provisional. Propose concrete endpoints, fields, request/response shapes, and status behavior when that helps resolve the design, giving rationale and an explicit `Proposed` status. Do not present proposals as existing or approved facts, or claim generated OpenAPI, provider behavior, test results, or approval evidence without evidence.

## Specify the contract

- State contract principles, resource identity, tenant/ownership scoping, and read/write consistency expectations. Explain public identifiers versus internal identity where relevant.
- Provide an access matrix by actor/role and resource/action. Include intentional omission of sensitive fields and generic responses where disclosure itself creates risk.
- Group operations by resource or workflow in endpoint/operation tables. For each meaningful operation show purpose, authorization, input/preconditions, success result, error/recovery behavior, and status/reference. Keep routes and verbs provisional unless approved.
- Give request and response shapes or concise JSON examples for nontrivial operations. Specify required/optional fields, field validation, projections by role, and omission/redaction rules. Avoid exposing internal implementation values as the public contract by default.
- Define a consistent error envelope and operation-specific error semantics, including malformed input, validation failure, authentication/authorization, absent/out-of-scope resources, business conflicts, stale state, rate limits, and temporary failure as applicable.
- Cover collection pagination/filtering/sorting, versioning/evolution, caching or conditional reads where relevant, concurrency/preconditions, retry/idempotency rules, and external side-effect boundaries. State which write behavior must align with a domain/database transaction boundary; flag the actual implementation mechanism for technical review.

## Finish well

List unresolved contract questions and review checks: UX state support, privacy projections, transaction behavior, API/database alignment, compatibility, security, and implementation verification. Cite only approved sources for confirmed behavior and label the rest.

After completing this design or a material revision, use the [optional independent design-review workflow](../sdlc/SKILL.md#offer-independent-design-review) to link the result, name the next lifecycle step, and offer a subagent review/stress test before normal approval.
