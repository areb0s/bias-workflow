# Implementation, Verification, and Completion

Under the [main/worker contract](../SKILL.md#mainworker-contract), workers implement, test, perform detailed reviews, and draft specification feedback. Main judges compact evidence reports, preserves decision/iteration continuity, and communicates completion or blocked status; evidence follow-ups return to workers. Worker failures and unavailable validation remain visible, not grounds for silent main execution or a success claim.

## Implementation

Implement the initially approved specification-plan pair or its evidence-backed in-scope successor under the approved feedback loop.

Preserve user work and current ownership boundaries. Reuse the named live references without copying unrelated structure. Do not add speculative abstractions, configuration, fallbacks, or refactors.

Continue autonomously through ordinary imports, type errors, formatting, and equivalent implementation details that do not change the approved contract or plan.

Revise the specification and plan before applying an evidence-backed correction within the approved goal, deliverable scope, explicit constraints, and permissions. Stop and seek a new combined approval when a discovery exceeds those boundaries; the loop does not authorize new user/product choices or unrelated work.

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

After each verification and before the final completion decision, evaluate the specification itself against the observed result, not only whether the implementation passed it. Feed supported corrections into the next iteration of the same request.

Include `명세 피드백` in the report, whether the work is complete or blocked:

- **Keep:** goals, constraints, and acceptance criteria supported by the outcome.
- **Discoveries:** omissions or ambiguities exposed by the result, citing the affected requirement and observed evidence. Separate observations from causal hypotheses.
- **Open questions:** what remains unknown and what evidence or user answer would resolve it. Unverified guesses are questions, not new requirements.
- **Next specification change:** the specific item to keep, revise, add, or remove, its reason, and the conditions under which it applies. Distinguish applied in-scope corrections from deferred or out-of-scope proposals. Preserve effective criteria rather than rewriting the entire specification.

Distinguish required corrections to the current work from optional proposals for subsequent work. An unmet current criterion remains a blocker; feedback cannot turn it into a future improvement and declare completion. Never weaken a criterion to make failed verification pass. New user or product choices follow the existing return-to-stage and combined-approval rules.

Initial combined approval authorizes supported in-scope specification and plan corrections followed by reimplementation within the loop below. Preserve user intent and explicit constraints. If no evidence supports a specification change, report `변경 제안 없음`; implementation defects may still need repair against the unchanged criteria. Do not invent lessons or demand another cycle.

### Iteration control (single owner)

- Count the first implementation/verification pass as iteration 1. Allow at most 30 passes for the current request, including that first pass. In-scope specification/plan revisions do not reset the count; ordinary edits or individual test commands are not separate iterations.
- After verification, choose exactly one outcome:
  - **Complete:** all completion conditions above hold and feedback identifies no required correction. Stop early; optional improvements do not require another pass.
  - **Continue:** a required correction has observed evidence, a concrete in-scope next action, and remaining budget. Revise only the affected specification/plan items, then reimplement and reverify. For a pure implementation defect, preserve the specification and correct the implementation. Recheck affected criteria and preserved behavior; retain still-valid prior evidence without presenting it as a fresh test run.
  - **Blocked:** stop when the latest corrective pass shows no evidence-backed improvement over the preceding pass, iteration 30 ends with required work remaining, or an unresolved blocker leaves no justified in-scope next action. An initial failure alone is not stagnation. Never relabel stagnation, exhaustion, unavailable validation, or an error as success. Boundary changes follow the existing combined-approval rules.
- Judge improvement by criterion-level evidence, resolved defects, or resolved specification ambiguity—not by rewriting prose or relaxing criteria. Record why continuing is justified; no numeric score gate is required.
- In the existing work report, retain a compact entry for each pass: iteration number, affected criteria, observed verification evidence/failures, specification/plan changes and reasons (or unchanged), and the continue/complete/blocked decision. Preserve earlier failure evidence; avoid repeating unchanged specifications and logs. Do not claim a reconstructed or unknown count as observed.

These are agent instructions, not runtime enforcement. Do not launch a separate session to restart the loop or reset its budget, add persistent counters, or create a memory/snapshot store. In-scope worker delegation follows the central contract and retains this request's iteration continuity. When feedback is available in a later request, follow [Specification](specification.md); it is evidence, not permission to resume old work.

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
- Complete or blocked, with reason and final iteration count (including the initial pass)

## 명세 피드백
- Keep, discoveries, open questions, and applied/deferred specification changes
- Compact iteration entries with evidence, change reasons, and decisions
- Or: 변경 제안 없음, with a brief reason

## Git 상태
- Working-tree changes
- Staged changes
- Commit observation
- Push observation
```

Do not describe `수정 완료` as `검증 완료`. Do not describe verified work as staged, committed, or pushed without observing those separate actions.
