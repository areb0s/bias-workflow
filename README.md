# bias-workflow

A contract-first Pi skill for moving coding work through:

```text
request → concretization → specification → implementation plan → approval → implementation → verification → completion
```

Concretization, specification, and planning remain distinct stages. Specification and plan are presented together for one explicit approval before product code is changed.

## Behavior

- Keeps fully specified mechanical edits concise while preserving separate specification and plan labels before approval.
- Asks one consequential clarification at a time when behavior, ownership, scope, or failure policy is unclear.
- Defines observable acceptance criteria before proposing code changes.
- Inspects live code before naming implementation files, symbols, ownership, and validation.
- Requests one combined approval for the current specification and implementation plan.
- Returns to the affected stage when implementation reveals a material new assumption.
- Separates implementation, verification, completion, staging, commit, and push states.
- Evaluates the specification against observed results, reporting what to preserve, evidence-backed gaps, unresolved questions, and proposals for the next specification.
- Reviews relevant available feedback in later specifications and explains what is incorporated, deferred, or excluded without automatically changing user intent or approved criteria.

## Specification feedback loop

```text
implementation + verification results
→ specification feedback: preserve / discoveries / open questions / next changes
→ review in the next relevant specification
→ combined specification-plan approval before implementation
```

Feedback lives in the existing completion report; this package does not automatically persist it across sessions. Later specification work uses related reports or feedback when available. There is no automatic re-execution, scoring threshold, or requirement to invent an improvement: `변경 제안 없음` is a valid outcome. Current unmet acceptance criteria remain blockers, not deferred improvements used to claim completion.

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
