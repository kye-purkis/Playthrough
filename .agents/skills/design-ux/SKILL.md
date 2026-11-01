---
name: design-ux
description: "Draft or update portable UX design records for an SDLC initiative, including journeys, states, accessibility, and optional design-language guidance."
---

# UX design

Produce or update `design/ux-design.md` for the active initiative. Produce `design/design-language.md` only when a project needs reusable visual and component guidance; do not create it merely to fill the document set.

Read relevant phase `questions.md` entries before drafting. Use [resolve-questions](../resolve-questions/SKILL.md) to record newly raised questions and unconfirmed assumptions, link their owning entries from this record, and reconcile answers through the concerned skills. The shared contract governs timestamps, raising/concerned skills, options, response history, and reconciliation status.

## Start with project evidence

Read [the shared document contract](references/document-contract.md) on **every invocation**, then read the PRD, requirements decisions, design decisions, domain model, and related UX/product material. Resolve the active initiative and retain established paths and terminology.

Use [the UX-design template](assets/ux-design-template.md) for the primary record. If design-language guidance is requested or materially useful, also use [the design-language template](assets/design-language-template.md). Preserve evidence and clear prior decisions; label unvalidated assumptions and proposals instead of inventing user research, approval, visual direction, or usability results.

## Describe observable experiences

- Map key journeys by role and surface. Each journey states the user goal, starting condition, ordered flow, decision/error points, completion outcome, and requirement or decision references.
- Specify relevant screen and interaction states: initial/loading, empty, populated, validation, permission denial, recoverable error, offline/unavailable where relevant, conflict/stale-data handling, retry behavior, and irreversible/destructive confirmation where relevant. Mark genuinely irrelevant states with a reason.
- Write content and feedback as intent and behavior, not invented product copy. State what information each role may see; do not expose sensitive details through errors, search, or shared-device flows.
- Include accessibility requirements that affect design: semantic structure, keyboard operation/focus, readable labels/errors, contrast and non-colour cues, touch targets, motion, zoom/reflow, localization, or assistive technology where relevant. Tie nonstandard needs to evidence or an open question.
- Keep product policy, design choices, and technical implementation separate. Link approved scope/rules; record proposed UX decisions and validation work without treating sketches or stated direction as approval.

## Optional design-language record

Use it only for a repeatable interface. Capture reference screens or system references, visual principles, tokens with `Token | Value | Use | Status`, component behavior/states, and responsive checks. Distinguish approved brand/product direction from illustrative proposals. Do not carry a previous project's palette, typography, imagery, or components into a new project.

## Finish well

List concrete validation and review questions, including untested journeys, accessibility checks, private-data exposure, and responsive behavior. Check journeys agree with the domain model and API/architecture records can support stated states without silently deciding mechanics.

After completing this design or a material revision, use the [optional independent design-review workflow](../sdlc/SKILL.md#offer-independent-design-review) to link the result, name the next lifecycle step, and offer a subagent review/stress test before normal approval.
