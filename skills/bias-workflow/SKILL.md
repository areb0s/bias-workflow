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
→ specification_feedback
  → completed (criteria met; no required correction)
  → specifying → planning → implementing (in-scope correction; budget remains)
  → blocked (no improvement, exhausted budget, or unresolved blocker)
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
8. Treat initial approval as covering the presented specification-plan pair and its bounded feedback loop, not unrelated work or expanded authority.
9. Implement only the approved scope. Do not add speculative state, configuration, helpers, wrappers, exports, fallbacks, or refactors.
10. Apply evidence-backed in-scope corrections through the feedback loop. If a discovery requires changing the approved goal, scope, explicit constraints, or permissions, stop and return to the affected stage rather than expanding authority.
11. Connect every completion claim to observed verification evidence.
12. Report implementation, verification, completion, staging, commit, and push as separate facts.
13. After each verification, evaluate specification feedback using the completion reference. Apply supported in-scope corrections to the specification and plan before reimplementation; preserve the iteration's evidence and change reasons.

## Material discoveries

Return to concretization when a new user or product decision is required. Return to specification when the understood request remains valid but its behavioral contract, scope, or failure policy must change.

Return to planning when implementation details or validation must change. The initially approved loop permits evidence-backed specification and plan revisions within its approved goal, deliverable scope, explicit constraints, and permissions without per-iteration approval.

When a discovery exceeds those boundaries, stop and present a revised specification-plan pair for one new combined approval. The loop is not permission to modify unapproved deliverables or make new user/product choices.

## Result-to-specification feedback

After verification, evaluate what the observed result teaches about the specification. [Completion](references/completion.md) owns the loop budget, continuation and stop decisions, and compact iteration evidence; [Specification](references/specification.md) owns incorporation into the next contract.

The agent follows this loop within the current request: implementation → verification → specification feedback → necessary specification/plan revision → reimplementation. Initial approval covers at most 30 implementation/verification iterations, including the first. This is skill guidance, not a runtime scheduler or enforced counter. Keep current blockers distinct from optional future improvements. Do not add a score gate, memory store, or mandatory change when evidence supports keeping the specification.

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
