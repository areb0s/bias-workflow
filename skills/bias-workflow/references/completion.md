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

## Specification feedback

After verification and the completion decision, evaluate the specification itself against the observed result, not only whether the implementation passed it. Use this bounded loop: evaluation → unresolved questions → proposed changes for the next specification.

Include `명세 피드백` in the report, whether the work is complete or blocked:

- **Keep:** goals, constraints, and acceptance criteria supported by the outcome.
- **Discoveries:** omissions or ambiguities exposed by the result, citing the affected requirement and observed evidence. Separate observations from causal hypotheses.
- **Open questions:** what remains unknown and what evidence or user answer would resolve it. Unverified guesses are questions, not new requirements.
- **Next specification proposal:** the specific item to keep, revise, add, or remove, its reason, and the conditions under which it applies. Preserve effective criteria rather than rewriting the entire specification.

Distinguish required corrections to the current work from optional proposals for subsequent work. An unmet current criterion remains a blocker; feedback cannot turn it into a future improvement and declare completion. Never weaken a criterion to make failed verification pass. New user or product choices follow the existing return-to-stage and combined-approval rules.

Feedback is a proposal, not an amendment to the approved contract or permission to execute another iteration. Preserve user intent and constraints. If no evidence supports a change, report `변경 제안 없음`; routine work may use that single line rather than filling empty sections. Do not invent lessons or demand another cycle.

Keep feedback in the existing completion report, tied to the task and its verification evidence. This skill does not create a new memory store, automatically persist rules, or start another run. When relevant feedback is available during a later specification, follow the feedback review in [Specification](specification.md).

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

## 명세 피드백
- Keep, discoveries, open questions, and next specification proposal
- Or: 변경 제안 없음, with a brief reason

## Git 상태
- Working-tree changes
- Staged changes
- Commit observation
- Push observation
```

Do not describe `수정 완료` as `검증 완료`. Do not describe verified work as staged, committed, or pushed without observing those separate actions.
