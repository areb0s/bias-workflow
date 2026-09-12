---
name: bias-workflow
description: Guides coding work through separate concretization, specification, and implementation-plan stages followed by one combined approval, implementation, verification, and completion. Use for coding requests, keeping fully specified mechanical changes concise while expanding ambiguous or architecture-affecting work as needed.
---

# Bias Workflow

Use a contract-first workflow without turning routine edits into ceremony.

## Route the request

Use the full workflow when the request has a material unresolved choice about user-visible behavior, scope, ownership, state, failure policy, or architecture.

For a fully specified mechanical edit, keep concretization brief and present concise, separately labeled specification and plan sections. Request their combined approval before editing. Never infer permission to stage, commit, push, publish, deploy, or discard work.

## Workflow owner

This skill owns progression through:

```text
received
→ clarifying
→ specifying
→ planning
→ awaiting_approval
→ implementing
→ verifying
→ completed
```

Concretization, specification, and implementation planning are distinct stages. Do not ask for approval between them. Ask once only after both the specification and plan are ready.

Read the matching reference before performing each stage:

- [Concretization](references/concretization.md)
- [Specification](references/specification.md)
- [Implementation plan](references/implementation-plan.md)
- [Approval](references/approval.md)
- [Completion](references/completion.md)

## Operating rules

1. Investigate facts that code, project instructions, tools, or prior approved decisions can answer before questioning the user.
2. During concretization, ask only one consequential question per turn.
3. Do not present implementation choices as requirements before the desired behavior and boundary are understood.
4. Complete the specification before writing the implementation plan.
5. Base the plan on current production code, its canonical owners, callers, consumers, and validation seams.
6. Present the specification and plan as separate sections in one approval packet.
7. Do not modify any requested product or deliverable file before approval, including code, tests, documentation, configuration, fixtures, and generated artifacts. Read-only exploration and explicitly requested non-product planning artifacts remain allowed.
8. Treat approval as applying only to the presented specification-plan pair.
9. Implement only the approved scope. Do not add speculative state, configuration, helpers, wrappers, exports, fallbacks, or refactors.
10. If implementation reveals a material new assumption, stop and return to the affected stage rather than silently expanding scope.
11. Connect every completion claim to observed verification evidence.
12. Report implementation, verification, completion, staging, commit, and push as separate facts.
13. After verification, report evidence-based specification feedback using the completion reference. Review relevant available feedback when drafting a later specification; proposals never silently amend the approved contract.

## Material discoveries

Return to concretization when a new user or product decision is required. Return to specification when the understood request remains valid but its behavioral contract, scope, or failure policy must change.

Return to planning when the contract remains valid but the approved owner, files, symbols, data flow, state changes, or validation approach must materially change.

After either return, present a revised specification-plan pair and request one new combined approval.

## Result-to-specification feedback

Alongside the completion decision, evaluate what the observed result teaches about the specification: what to preserve, what was missing or ambiguous, what remains unknown, and what to propose for the next specification. [Completion](references/completion.md) owns this feedback; [Specification](references/specification.md) owns its review and incorporation when relevant feedback is available.

This is a feedback path, not an automatic execution loop. Keep current blockers distinct from future improvements, preserve user intent, and use the existing combined approval for a revised specification-plan pair. Do not add a score gate, memory store, or mandatory change when evidence supports keeping the specification.

## Output labels

Use explicit labels so proposals are not confused with completed work:

- `현재 상태`
- `구체화`
- `명세`
- `구현 계획`
- `승인 요청`
- `수정 완료`
- `검증`
- `완료 판정`
- `명세 피드백`
- `Git 상태`
