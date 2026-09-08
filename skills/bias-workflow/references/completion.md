# Implementation, Verification, and Completion

## Implementation

Implement only the approved specification-plan pair.

Preserve user work and current ownership boundaries. Reuse the named live references without copying unrelated structure. Do not add speculative abstractions, configuration, fallbacks, or refactors.

Continue autonomously through ordinary imports, type errors, formatting, and equivalent implementation details that do not change the approved contract or plan.

Stop when a material discovery changes behavior, ownership, state, scope, failure policy, target layers, or validation. Return to the affected stage and seek a new combined approval.

## Deletion review

Before verification, review changed code for:

- removable state;
- unused parameters or exports;
- one-call wrappers that obscure rather than clarify;
- duplicated guards, retries, votes, or fallbacks;
- impossible-state defenses outside real boundaries;
- obsolete code left behind by the change;
- names that require implementation knowledge to understand.

Simplify only within the approved scope.

## Verification

Map observed evidence to each acceptance criterion. Report exact commands or manual checks and their results.

Separate:

- passing evidence;
- regressions caused by the change;
- pre-existing failures;
- environment-specific failures;
- unverified or manual-only criteria.

Never claim a check was run when it was not observed. A failed required check prevents completion unless the contract explicitly accepts that failure.

## Completion decision

Mark the work complete only when:

- every acceptance criterion has supporting evidence;
- preserved behavior remains intact;
- no unresolved change-caused failures remain;
- the implementation remains within approved scope;
- required documentation and tests match current behavior;
- residual risks and evidence gaps are disclosed.

## Completion report

Use distinct sections:

```markdown
## 수정 완료
- What changed

## 의도적으로 제외
- Approved non-goals

## 검증
- Evidence and results

## 완료 판정
- Complete or blocked, with reason

## Git 상태
- Working-tree changes
- Staged changes
- Commit observation
- Push observation
```

Do not describe `수정 완료` as `검증 완료`. Do not describe verified work as staged, committed, or pushed without observing those separate actions.
