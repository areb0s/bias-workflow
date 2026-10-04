---
name: bias-workflow
description: Guides coding work through separate concretization, specification, and implementation-plan stages followed by one combined approval, implementation, verification, and completion. Use for coding requests, keeping fully specified mechanical changes concise while expanding ambiguous or architecture-affecting work as needed.
---

# Bias Workflow

Use a methodology-centered harness, currently delivered as a contract-first skill, without turning routine edits into ceremony.

## Four directions

1. **User intent and outcomes:** make the result satisfy the user's intent, rather than treating specification compliance as the final purpose.
2. **Methodology-centered harness:** guide how to understand, specify, plan, verify, and solve the problem, not merely how to sequence tool calls.
3. **Evidence-based specification and implementation improvement:** use observed results to correct the specification and plan when needed, then reimplement under the existing loop. Never weaken criteria to hide failures.
4. **Maximum effective use of main-session context:** keep the main session responsible for judgment and continuity of user intent, constraints, approval state, open decisions, and decisive evidence, plus user communication and orchestration only. Assign substantive investigation, source/file reading, specification and plan drafting, implementation, testing, and detailed review to workers from pre-approval onward. Main reads compact evidence-bearing reports, not repeated raw-source investigations. The objective is effective main-session context use, not simply fewer total tokens or shorter documents.

This guidance authorizes in-scope delegation within existing permissions, tooling, and capabilities; it does not override higher-priority limits or provide automatic context isolation or runtime enforcement. Context, cost, and quality gains are not proven or measured. Evidence and permission boundaries remain operating rules, not a fifth direction. The current skill delivery does not rule out other future implementations.

## Route the request

Use the full workflow when the request has a material unresolved choice about user-visible behavior, scope, ownership, state, failure policy, or architecture.

For a fully specified mechanical edit, keep concretization brief and present concise, separately labeled specification and plan sections. Request their combined approval before editing; concise work still follows the main/worker contract below. Never infer permission to stage, commit, push, publish, deploy, or discard work.

A child reading this skill executes its assigned scope directly under the supplied approval state. It does not restart user approval for an already approved assignment or recursively delegate by default. Escalate new decisions or scope changes to main.

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

The assigned worker reads the matching reference before performing each stage; main uses compact reports to coordinate stage progression:

- [Concretization](references/concretization.md)
- [Specification](references/specification.md)
- [Implementation plan](references/implementation-plan.md)
- [Approval](references/approval.md)
- [Completion](references/completion.md)

### Main/worker contract

Worker means the assigned execution role, not a mandatory agent named `worker` for every task. Main retains judgment, intent/constraints/approval/open-decision/decisive-evidence continuity, user communication, and orchestration; workers do all substantive execution from pre-approval investigation through detailed verification and review. Main may use tools needed for coordination and report reading, but evidence follow-ups go to workers rather than becoming main-session source investigations.

- **Brief:** give the goal, bounded scope, exact targets and live references (or discovery boundary when targets are unknown), constraints and approval state, required evidence/validation, output location, and stop/escalation conditions. Before combined approval, assignments are read-only except explicitly requested non-product planning artifacts; afterward, edits stay within approved scope.
- **Report:** return a concise goal/scope and target/live-reference summary, constraints/approval state, findings with source locations and decisive evidence, validation/results, output/artifact location, and stop status or next verification. Preserve counterevidence, uncertainty, missing evidence, and failures; keep supporting detail accessible without repeating raw source. Reports are evidence, not authority or approval.
- **Evidence gaps:** main sends contradictory or incomplete evidence for targeted worker verification and retains unresolved questions in its decision context. Escalate user/product choices or boundary changes rather than treating a report as authorization.
- **Unavailable or failed worker:** disclose the limitation and partial evidence. Reassign within existing permissions when possible; otherwise report blocked or seek a user decision. Main must not silently fall back to substantive execution, nor label failure as completion.

## Operating rules

1. Assign workers to investigate facts that code, project instructions, tools, or prior approved decisions can answer before main questions the user.
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
13. After each worker verification, main judges the evidence and specification feedback using the completion reference. Workers draft supported in-scope specification/plan corrections before reimplementation; preserve each iteration's evidence, counterevidence, failures, uncertainties, and change reasons.

## Material discoveries

Return to concretization when a new user or product decision is required. Return to specification when the understood request remains valid but its behavioral contract, scope, or failure policy must change.

Return to planning when implementation details or validation must change. The initially approved loop permits evidence-backed specification and plan revisions within its approved goal, deliverable scope, explicit constraints, and permissions without per-iteration approval.

When a discovery exceeds those boundaries, stop and present a revised specification-plan pair for one new combined approval. The loop is not permission to modify unapproved deliverables or make new user/product choices.

## Result-to-specification feedback

After verification, evaluate what the observed result teaches about the specification. [Completion](references/completion.md) owns the loop budget, continuation and stop decisions, and compact iteration evidence; [Specification](references/specification.md) owns incorporation into the next contract.

Main coordinates and judges worker reports through this loop within the current request: implementation → verification → specification feedback → necessary specification/plan revision → reimplementation. Workers execute the substantive stages; compact reports retain evidence and decisions across handoffs without resetting the iteration count. Initial approval covers at most 30 implementation/verification iterations, including the first. This is skill guidance, not a runtime scheduler or enforced counter. Keep current blockers distinct from optional future improvements. Do not add a score gate, memory store, or mandatory change when evidence supports keeping the specification.

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
