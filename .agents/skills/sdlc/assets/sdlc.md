# Software development lifecycle

**Status:** [Agreed / Draft] · **Scope:** [What this lifecycle governs]

Use this lifecycle for each feature or delivery slice. Keep records proportional to change size and risk. Revisit earlier records when evidence changes a decision.

| Stage | Activities | Output and checkpoint |
| --- | --- | --- |
| 1. Requirements | Define problem, users, outcomes, scope, rules, risks, and open questions. Write testable requirements and measures. | Approved PRD and requirements decisions. |
| 2. Design | Define domain, journeys, architecture, API, database, trade-offs, and risky assumptions; optionally prototype key journeys to support UX review. | Reviewed design records and design decisions. |
| 3. Build | Order usable slices; implement, review, and verify them. | Delivery backlog, verification record, build decisions, and demonstrated slices. |
| 4. Release and learn | Prepare rollout and support; observe outcomes and feedback. | Release record, release decisions, and a continue/adjust/stop decision. |

## Named deliverables

Use `docs/initiatives/<initiative>/` unless the project has an established equivalent path. Keep `decisions.md` and `questions.md` in each phase directory. Create only defined lifecycle records or explicitly linked established equivalents; handoff and reconciliation information belongs in these records and the task report.

| Stage | Deliverables |
| --- | --- |
| Requirements | `requirements/prd.md`, `requirements/decisions.md`, `requirements/questions.md` |
| Design | `design/domain-model.md`, `design/ux-design.md`, `design/design-language.md` when prototyping (otherwise optional), `design/architecture-design.md`, `design/api-design.md`, `design/database-design.md`, `design/decisions.md`, `design/questions.md`; optional prototype linked from the UX record |
| Build | `build/delivery-backlog.md`, `build/verification-record.md`, `build/decisions.md`, `build/questions.md` |
| Release | `release/release-record.md`, `release/decisions.md`, `release/questions.md` |

## Working agreements

1. Product-owner PRD approval comes before detailed design. Design review is required for core domain rules, user journeys, security, or deployment changes. Before asking for detailed written UX review or approval, offer a prototype as an optional design deliverable, unless the user has already chosen for the current scope. It can be the main review surface with the UX record as supporting detail. Record acceptance, decline or deferral in the UX record. Before implementing or delegating a selected prototype, read the existing design-language document or create it first and agree missing visual direction with the owner. Then create and walk through the scoped prototype and link its evidence/limits for UX review; declining it adds no deliverable or approval gate.
2. Keep one PRD per substantial feature or release; small changes may stay in the relevant story. Maintain a `decisions.md` in every phase, even before decisions exist. Use stable phase decision IDs: `REQ-###`, `DES-###`, `BLD-###`, and `REL-###`. Never reuse or renumber them. Record date, decision or proposal, source, status, and rationale. Distinguish product-owner decisions from implementer choices and proposals; link decision IDs to their phase files. When later evidence changes an earlier choice, record its amendment or supersession and reconcile affected earlier records without erasing history.
3. A story is ready with a clear outcome, criteria, dependencies, and needed design decisions. A task is ready with purpose and completion checks.
4. A slice is done only after its criteria are demonstrated, relevant checks pass, required review and operational/documentation work are complete, and the product owner accepts it.
5. Scope approval, design review, technical verification, delivered-slice acceptance, and release readiness are separate checkpoints. Keep planned work separate from observed results; record missing evidence as pending or unknown.
6. Compare release outcomes and feedback with PRD success measures. Record the accountable owner's decision to continue, adjust, or stop, and feed findings into the next requirements cycle.
7. Track open questions and unconfirmed assumptions in each phase's `questions.md`, with stable IDs (`REQ-Q-###`/`REQ-A-###`, `DES-Q-###`/`DES-A-###`, `BLD-Q-###`/`BLD-A-###`, `REL-Q-###`/`REL-A-###`), statement, actual timestamp with timezone, raising skill, concerned skills and record links, practical answer options, response history and reconciliation state. Assumptions may be resolved by explicit approval. Link to owning entries from other records instead of duplicating tracking.
8. A request for open questions lists all phases or the specified phase, including unconfirmed assumptions and separately any answered items still awaiting reconciliation, then offers guided resolution. Record each answer and reconcile through concerned skills, using independent subagents where possible and one coordinator for shared logs. Keep reconciliation tracking in the owning question entry; a recorded answer alone does not prove all affected records agree or that broader approvals/checks passed.
9. Continue the requested work within its authorized scope until completion or a concrete blocker, user change, or user stop. If incomplete, report its unmet condition and blocker before proposing follow-on work.
