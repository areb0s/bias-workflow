# Combined Approval

Request approval once, after the specification and implementation plan are both complete.

## Approval packet

Present:

```markdown
## 현재 상태
승인 대기

## 명세
### Goal
...
### Current behavior
...
### Required behavior
...
### Preserved behavior
...
### Acceptance criteria
...
### Failure policy
...
### Non-goals
...
### Evidence gaps
...

## 구현 계획
### Data flow
...
### Ownership
...
### State changes
...
### Functions and names
...
### Removed code
...
### Failure policy placement
...
### Non-goals
...
### Validation
...
### Expected staging units (when applicable)
...
### Escalation conditions
...

## 승인 요청
위 명세와 구현 계획을 기준으로 구현을 진행할까요?
```

Keep specification and plan visibly separate even though they share one approval.

## Approval semantics

Approval applies only to the presented specification-plan pair. It grants permission to modify the approved deliverable scope, including whichever code, tests, documentation, configuration, fixtures, or generated artifacts the packet names. It does not grant permission to stage, commit, push, publish, deploy, delete unrelated work, or discard user changes.

A clear implementation request may approve the packet. Ambiguous feedback or discussion does not.

## Revisions

If the user changes required behavior, return to specification and re-evaluate the plan.

If the user changes only implementation scope or approach, return to planning while preserving the valid specification.

After either change, present the revised pair and request one new combined approval. Do not ask for separate specification and plan approvals.

## Before implementation

Confirm that:

- no material uncertainty remains;
- acceptance criteria are observable;
- exact owners and targets are identified from current code;
- non-goals prevent adjacent scope growth;
- validation is focused and sufficient;
- the user has explicitly approved the current pair.
