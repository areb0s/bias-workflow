# bias-workflow

A contract-first Pi skill for moving coding work through:

```text
request → concretization → specification → implementation plan → approval
→ implementation → verification → specification feedback
  → completion
  → in-scope specification/plan revision → reimplementation → verification
  → blocked
```

Concretization, specification, and planning remain distinct stages. Specification and plan are presented together for one explicit approval before product code is changed.

## Behavior

- Keeps fully specified mechanical edits concise while preserving separate specification and plan labels before approval.
- Asks one consequential clarification at a time when behavior, ownership, scope, or failure policy is unclear.
- Defines observable acceptance criteria before proposing code changes.
- Inspects live code before naming implementation files, symbols, ownership, and validation.
- Requests one combined approval for the initial specification-plan pair and a bounded feedback/reimplementation loop.
- Revises supported in-scope specification and plan items without per-iteration approval; changes beyond the approved goal, deliverable scope, explicit constraints, or permissions still require approval.
- Separates implementation, verification, completion, staging, commit, and push states.
- Evaluates the specification against observed results and applies necessary evidence-backed corrections before reimplementation, preserving effective criteria and unresolved evidence gaps.
- Reviews relevant available feedback in later specifications and explains what is incorporated, deferred, or excluded without automatically changing user intent or approved criteria.

## Specification feedback loop

```text
implementation + verification results
→ specification feedback: preserve / discoveries / open questions / next changes
→ complete if criteria are met and no required correction remains
→ otherwise revise affected specification/plan items within approved boundaries
→ reimplement and reverify while improvement and budget permit
→ report blocked on stagnation, exhaustion, or an unresolved blocker
```

The agent follows at most **30 implementation/verification iterations, including the initial pass**, under the initial approval. Stop early on success; stop as blocked when a corrective pass shows no evidence-backed improvement, the budget is exhausted with required work remaining, or no justified in-scope next action is available. [Completion](skills/bias-workflow/references/completion.md) owns the exact counting and stop rules.

Feedback and compact per-iteration evidence, change reasons, and decisions live in the existing report; this package does not automatically persist them across sessions. Later specification work uses related feedback when available, not as permission to resume old work. There is no scoring threshold or requirement to invent an improvement: `변경 제안 없음` is valid. Implementation defects can be repaired without changing the specification. Current unmet criteria remain blockers, not deferred improvements or criteria to weaken to claim completion.

This is a skill-guided same-request loop, not an automatic runtime scheduler or enforced iteration limit. It adds no separate user-choice handling system; existing scope and permission boundaries remain in force.

This package does not add runtime gates, durable workflow state, UI, issue publishing, or automatic Git actions.

## Install

```bash
pi install /path/to/bias-workflow
```

Use it automatically for matching work or invoke it explicitly:

```text
/skill:bias-workflow
```

## Verify

```bash
npm run check
```
