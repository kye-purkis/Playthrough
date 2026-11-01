---
name: sdlc
description: Coordinate a documented software-development initiative through requirements, design, build, and release, including phase questions, assumptions, and reconciliation of answers. Use when setting up, assessing, or advancing SDLC records; use specialist skills for the actual deliverables.
---

# SDLC coordinator

Read [the shared document contract](references/document-contract.md) at the start of **every** run. It governs paths, IDs, evidence, approvals, traceability, and checkpoints. Then inspect the relevant project records before proposing or making changes.

Before committing, pushing, opening or updating a pull request, or merging, follow the [Git workflow skill](../git-workflow/SKILL.md). SDLC planning and implementation approvals do not by themselves authorize publication.

## Route the work

Resolve the project root, initiative, existing conventions, the requested change, and its current evidence. Keep the documentation proportional: a substantial feature or release normally needs the full initiative record; a small change may remain in its existing story.

Create or revise lifecycle files only at a canonical path defined here or in the shared contract, or at an explicitly linked established equivalent. Do not create ad hoc handoff, status, summary, or next-steps files. Put handoff information in the relevant lifecycle records and the task report.

Use this map for the canonical record or the project’s explicitly linked equivalent:

| Stage | Record | Specialist skill |
| --- | --- | --- |
| Requirements | `requirements/prd.md` | [write-prd](../write-prd/SKILL.md) |
| Requirements | `requirements/decisions.md` | [record-decision](../record-decision/SKILL.md) |
| Requirements | `requirements/questions.md` | [resolve-questions](../resolve-questions/SKILL.md) |
| Design | `design/domain-model.md` | [design-domain](../design-domain/SKILL.md) |
| Design | `design/ux-design.md`, optional `design/design-language.md`, and optional prototype linked from the UX record | [design-ux](../design-ux/SKILL.md) |
| Design | `design/architecture-design.md` | [design-architecture](../design-architecture/SKILL.md) |
| Design | `design/api-design.md` | [design-api](../design-api/SKILL.md) |
| Design | `design/database-design.md` and optional schema/ERD records | [design-database](../design-database/SKILL.md) |
| Design | `design/decisions.md` | [record-decision](../record-decision/SKILL.md) |
| Design | `design/questions.md` | [resolve-questions](../resolve-questions/SKILL.md) |
| Build | `build/delivery-backlog.md` | [write-backlog](../write-backlog/SKILL.md) |
| Build | `build/verification-record.md` | [record-verification](../record-verification/SKILL.md) |
| Build | `build/decisions.md` | [record-decision](../record-decision/SKILL.md) |
| Build | `build/questions.md` | [resolve-questions](../resolve-questions/SKILL.md) |
| Release | `release/release-record.md` | [record-release](../record-release/SKILL.md) |
| Release | `release/decisions.md` | [record-decision](../record-decision/SKILL.md) |
| Release | `release/questions.md` | [resolve-questions](../resolve-questions/SKILL.md) |

Read the selected specialist skill before carrying out its work. If it is unavailable, still preserve the contract and report the missing capability; do not replace it with invented approval or evidence.

For delivery backlogs, use write-backlog’s [compact user-story and technical-task templates](../write-backlog/assets/delivery-backlog.md). Keep each item to one outcome, a short summary, essential links/dependencies, and observable criteria or checks; link supporting detail rather than repeating it.

Use [resolve-questions](../resolve-questions/SKILL.md) to capture questions and assumptions, list unresolved items for an initiative or phase, guide the user through answers when requested, and reconcile new answers across concerned skills. Listing ends with an offer to guide resolution; an answer or assumption approval triggers reconciliation in the same workflow. Keep all tracking in phase `questions.md` files, with links from affected records.

Apply the [current-phase interview guardrail](../resolve-questions/SKILL.md#keep-the-interview-within-the-current-phase) before extending a requirements interview. Keep a finite queue of owner decisions, route delivery mechanisms to design/operations, and consolidate the PRD for its normal approval checkpoint when substantive requirements choices are exhausted.

## Coordinate checkpoints

Make the next useful action concrete. Requirements need product-owner approval before detailed design; changes to core domain rules, journeys, security, or deployment need design review; a delivered slice needs demonstrated criteria, relevant passing checks, needed review and operational/documentation work, and product-owner acceptance. Release planning is distinct from releasing.

At every established SDLC checkpoint, state what is ready, link the concrete reviewable result, identify the checkpoint's approval or evidence still needed, and name the next step. For an owner approval, explicitly ask for the decision on that result rather than merely saying it is ready for review. At the requirements checkpoint, ask whether the product owner approves the linked consolidated PRD for the stated scope, and explain that detailed design follows approval. Do not treat completion of the interview as PRD approval.

Once a checkpoint is satisfied by its required evidence and approvals, record the outcome, reconcile affected records, and ask whether the user would like to continue to the named next step. Start that step only after authorization, unless the user already authorized proceeding within that scope; in that case state the next step and continue without redundant confirmation. Owner approval, demonstrated technical checks, slice acceptance and release authorization remain distinct: a request to continue cannot substitute for missing evidence or authorize an external release by implication.

Treat the user's requested work as the current unit of delivery. Continue it within the authorized scope until its stated completion conditions are met, the user changes or stops it, or a concrete blocker prevents further progress. Do not stop after partial implementation, planning, or documentation and describe the unfinished portion merely as a later "next action." When blocked, report the work as incomplete, identify the unmet completion condition and blocker, and name the specific action needed to resume. A next useful action follows completed requested work or resolves a clearly reported blocker.

Drafting, analysis, and consistency checks may continue while a checkpoint is pending. Label preliminary material and missing evidence accurately. Do not repeatedly seek approval already given within its stated scope; ask only when an unresolved approval or fact blocks a dependent action. Apply this interaction at established phase or slice checkpoints, not after every artifact edit. Continue independent authorized work while dependent work waits, and keep question batches progressing automatically until a genuine checkpoint; do not reopen settled questions.

When setting up a new initiative, copy and adapt [the portable SDLC template](assets/sdlc.md) to `docs/sdlc.md` only when the project has no equivalent lifecycle guide. Scaffold `decisions.md` and `questions.md` in all four phases when creating the initiative structure. Use the [questions template](../resolve-questions/assets/questions.md). Never overwrite established conventions or create a second source of truth.

## Offer a prototype during UX design

Treat a prototype as an optional design deliverable that can make a substantial UX design easier to review. Before asking the owner for a detailed review or approval of the written UX, briefly explain the proposed flows and ask whether a prototype would help. Use the [UX prototype-choice workflow](../design-ux/SKILL.md#offer-a-prototype-before-ux-approval). Respect an existing request, acceptance, decline or deferral for the current scope; do not ask again merely because another skill takes over. If selected, the prototype can be the main review surface, with the UX record providing supporting rules, states and traceability. Link the artifact and actual walkthrough results/limits from that record. Declining it adds no deliverable or approval gate; creating it does not itself approve the UX.

## Offer independent design review

After completing each design or material revision, treat its supporting records as one review scope. Link the concrete reviewable artifact or bundle, name the next lifecycle step, and offer an independent review before normal approval: “Would you like an independent subagent to review and stress-test this <design> and have me address any valid concerns before approval?” Substitute the design's name. This is optional, not an additional approval checkpoint; do not repeat it after minor edits or for a scope already reviewed, authorized or declined unless materially changed. If review is already authorized, carry it out without asking again. A decline returns to the normal approval/checkpoint flow.

Acceptance authorizes a scoped review and corrections, not design approval or permission to start the next phase. Give an independent subagent the applicable design skill, approved requirements and current decisions, the design and relevant dependencies, and representative normal, failure and boundary scenarios. Request read-only findings with evidence, impact and suggested corrections; do not prescribe conclusions or let the reviewer change shared records.

Validate findings against the governing requirements and decision authority. Correct valid concerns and reconcile directly affected canonical records within scope; do not silently change product decisions. Record unresolved owner choices through [resolve-questions](../resolve-questions/SKILL.md), and use [record-decision](../record-decision/SKILL.md) for material decisions or changes. Keep review outcomes, fixes, remaining risks and evidence/limits in the existing design/review sections rather than extra handoff files. Have consequential fixes rechecked with a focused review; report remaining concerns instead of cycling indefinitely.

Report what was actually reviewed and corrected, then return to the normal approval and continuation rules above. Do not claim an unavailable or unrun review completed, or imply conceptual review proves implementation, performance, security testing or provider correctness. Required evidence and owner approvals remain separate.

## Handoff

Before reporting, check that records use canonical or linked established paths, cross-links resolve, IDs were preserved, decisions show authority/status, and requirements connect to stories, evidence, and release outcomes as applicable. Do not create a separate handoff artifact for this report. Report changed records, the completion status of the requested work, current stage, unmet checkpoints, and the next usable action. If the requested work is incomplete, state that before listing any next action. At a checkpoint, include the explicit approval request or continuation question required above; naming a next action alone is insufficient.
