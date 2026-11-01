---
name: design-ux
description: "Draft or update portable UX design records for an SDLC initiative, including journeys, states, accessibility, and optional design-language guidance."
---

# UX design

Produce or update `design/ux-design.md` for the active initiative. Before implementing a prototype, use an existing linked design-language record or create `design/design-language.md` to establish its visual and component direction. Outside prototyping, create that record only when reusable guidance is useful.

Read relevant phase `questions.md` entries before drafting. Use [resolve-questions](../resolve-questions/SKILL.md) to record newly raised questions and unconfirmed assumptions, link their owning entries from this record, and reconcile answers through the concerned skills. The shared contract governs timestamps, raising/concerned skills, options, response history, and reconciliation status.

## Start with project evidence

Read [the shared document contract](references/document-contract.md) on **every invocation**, then read the PRD, requirements decisions, design decisions, domain model, and related UX/product material. Resolve the active initiative and retain established paths and terminology.

Use [the UX-design template](assets/ux-design-template.md) for the primary record. When establishing design language, use [the design-language template](assets/design-language-template.md). Preserve evidence and clear prior decisions; label unvalidated assumptions and proposals instead of inventing user research, approval, visual direction, or usability results.

## Describe observable experiences

- Map key journeys by role and surface. Each journey states the user goal, starting condition, ordered flow, decision/error points, completion outcome, and requirement or decision references.
- Specify relevant screen and interaction states: initial/loading, empty, populated, validation, permission denial, recoverable error, offline/unavailable where relevant, conflict/stale-data handling, retry behavior, and irreversible/destructive confirmation where relevant. Mark genuinely irrelevant states with a reason.
- Write content and feedback as intent and behavior, not invented product copy. State what information each role may see; do not expose sensitive details through errors, search, or shared-device flows.
- Include accessibility requirements that affect design: semantic structure, keyboard operation/focus, readable labels/errors, contrast and non-colour cues, touch targets, motion, zoom/reflow, localization, or assistive technology where relevant. Tie nonstandard needs to evidence or an open question.
- Keep product policy, design choices, and technical implementation separate. Link approved scope/rules; record proposed UX decisions and validation work without treating sketches or stated direction as approval.

## Establish design language before prototyping

Before any prototype implementation or delegation, locate the project's design-language document or explicitly linked equivalent and read its applicable direction. If none exists, create `design/design-language.md` first. Establish references and visual principles, tokens with `Token | Value | Use | Status`, component behavior/states, and responsive checks before building screens.

Use existing owner-approved brand/product direction. If it is missing or ambiguous, ask for references/preferences or present a small set of proposed directions and obtain agreement on the direction before prototype implementation. A document full of unconfirmed tokens does not establish the desired design. Preserve any existing agreement; do not ask again for the same scope. Clearly distinguish agreed direction, proposed details and unvalidated checks. Do not infer visual preferences from product requirements, invent a desired palette/style, or copy another project's design language.

Pass the design-language record and its authority/status to any prototype implementer. Reconcile the prototype to that record and record any material departures for review; do not retroactively label an invented prototype style as approved direction. This prerequisite applies when a prototype is selected and does not make prototypes mandatory.


## Offer a prototype before UX approval

A prototype is an optional design deliverable intended to make the UX easier to understand and review. Once the main journeys and screens can be outlined in plain language, ask: “Would you like a prototype as an optional deliverable to help review these UX flows?” Ask before expecting the owner to review or approve a substantial written UX design; reading or approving the full document is not a prerequisite. Respect a choice or instruction already given for the current scope; do not repeat the question after a handoff, review or minor correction. Offer it before the optional independent review so a selected prototype can be included.

If selected, first complete the [design-language prerequisite](#establish-design-language-before-prototyping), then use the prototype as the main review surface when that suits the user, with the UX record supplying supporting detail and traceability. Create a scoped, reviewable artifact using appropriate available skills/tools; choose wireframes or clickable interactions to suit the question being tested and the user's preferences. Cover the relevant main flow, consequential failure/empty/permission states, and phone/desktop behaviour where applicable. Identify mock data and simulated payments/services, record what was actually walked through, and reconcile valid findings into the UX design. Do not treat a plan, screenshots or an untested prototype as proof of interactions or usability. Creation does not imply publication, production integration, UX approval or permission to start the next phase.

Link the optional deliverable from the UX record, using an established local artifact location or the selected tool’s artifact link. Record the choice, review approach, scope, observed results and remaining limits there; use the existing phase questions/decisions workflow for the response where needed. If declined, record that choice and proceed to normal review/approval without adding a prototype gate. If deferred, retain the stated revisit point and do not silently treat it as a decline or claim prototype work complete.

## Finish well

List concrete validation and review questions, including untested journeys, accessibility checks, private-data exposure, and responsive behavior. Check journeys agree with the domain model and API/architecture records can support stated states without silently deciding mechanics.

After completing this design or a material revision, use the [optional independent design-review workflow](../sdlc/SKILL.md#offer-independent-design-review) to link the result, name the next lifecycle step, and offer a subagent review/stress test before normal approval.
