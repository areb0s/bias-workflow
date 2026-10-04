# bias-workflow

A methodology-centered harness for coding agents, currently delivered as a contract-first Pi skill.

## Four directions

1. **User intent and outcomes:** aim for results that satisfy the user's intent, not merely a passing specification.
2. **Methodology-centered harness:** guide how the agent understands, specifies, plans, verifies, and solves a problem—not just which tools it calls.
3. **Evidence-based specification and implementation improvement:** use observed results to revise the specification and plan where needed, then reimplement. Never weaken criteria to hide failures.
4. **Maximum effective use of main-session context:** main owns judgment, continuity of intent/constraints/approval/open decisions/decisive evidence, user communication, and orchestration only. Workers perform substantive investigation, source/file reading, specification and plan drafts, implementation, testing, and detailed review from pre-approval onward. Main reads compact evidence-bearing reports and routes evidence follow-ups to workers, not repeated raw-source investigations. This is not simply minimizing total tokens or document length.

These are the agreed directions, not four measured capabilities. The guidance authorizes in-scope delegation within existing permissions, tooling, and capabilities, without overriding higher-priority limits. It does not implement automatic context isolation or routing, and context, cost, and quality gains are not proven or measured. Evidence and permission rules remain operating rules, not a separate fifth direction. A skill is the current delivery form, not a requirement that the harness must always remain skill-only.

## Workflow

Move coding work through:

```text
request → concretization → specification → implementation plan → approval
→ implementation → verification → specification feedback
  → completion
  → in-scope specification/plan revision → reimplementation → verification
  → blocked
```

Concretization, specification, and planning remain distinct stages. Specification and plan are presented together for one explicit approval before any requested deliverable is changed; worker investigation before approval stays read-only except explicitly requested non-product planning artifacts.

The central [main/worker contract](skills/bias-workflow/SKILL.md#mainworker-contract) defines concise assignments and evidence reports: goal, scope, exact targets/live references, constraints/approval state, evidence/validation, output location, and stop conditions. Worker is an assigned execution role, not a mandatory agent name. A child executes its assignment directly without default recursive delegation or reapproval of an already approved scope. Main may use coordination/report-reading tools, but does not take over substantive execution when a worker fails or is unavailable: disclose partial evidence, reassign within permissions, or report blocked/seek a decision. Preserve counterevidence, uncertainties, and failures; reports inform judgment but do not grant authority. Contradictory or incomplete evidence requires targeted worker verification.

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

Main retains feedback continuity and judges compact worker reports, while workers draft corrections and perform reimplementation/verification. Preserve each iteration's counterevidence, uncertainties, and failures; handoffs do not reset the budget. Feedback and compact per-iteration evidence, change reasons, and decisions live in the existing report; this package does not automatically persist them across sessions. Later specification work uses related feedback when available, not as permission to resume old work. There is no scoring threshold or requirement to invent an improvement: `변경 제안 없음` is valid. Implementation defects can be repaired without changing the specification. Current unmet criteria remain blockers, not deferred improvements or criteria to weaken to claim completion.

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
