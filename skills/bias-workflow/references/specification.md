# Specification

The specification defines what must be true for the request to be complete. It is a behavioral contract, not an implementation plan.

## Review prior specification feedback

When related completion reports or user-provided feedback are available, review their specification feedback before drafting the next contract. Do not assume feedback was persisted or recoverable; its absence does not block ordinary specification work or justify inventing a retrospective.

- Check each relevant proposal against the current request, code, and observed evidence. Preserve its task context and applicability conditions rather than treating it as a universal rule.
- State which proposals are incorporated, deferred pending evidence or a user answer, or excluded, with a brief reason and a reference to the originating feedback. Keep this note concise; omit it when no relevant feedback is available.
- Incorporate supported changes into the appropriate goal, behavior, constraint, acceptance criterion, or non-goal. Carry unresolved questions into evidence gaps or return to concretization when they require a consequential user decision.
- Preserve effective criteria and explicit user constraints. Feedback cannot override the user's current intent or lower the bar merely because an implementation failed. Record any in-scope amendment and its supporting evidence before implementation.

The initial specification and implementation plan require combined approval. That approval includes the bounded current-request loop owned by [Completion](completion.md): supported revisions within the approved goal, deliverable scope, explicit constraints, and permissions may proceed without per-iteration approval. Revise only affected items, preserve effective criteria, and update the plan before reimplementation. Changes beyond those boundaries still require a revised pair and new approval. Feedback from an earlier request grants no authority to execute a new one and does not require inventing another cycle.

## Required sections

### Goal

State the observable final outcome from the user's perspective.

### Current behavior

Describe only the current behavior relevant to the requested change.

### Required behavior

List observable behavior, inputs, outputs, and state transitions. Use the project's domain language.

### Preserved behavior

Name behavior that must remain unchanged, especially consumers adjacent to the requested change.

### Acceptance criteria

Write independently checkable conditions. Each condition must be capable of producing evidence during verification.

### Failure policy

State when the behavior rejects, omits, defers, retries, or falls back. Assign each stabilization decision to one owner.

### Non-goals

List nearby changes that the contract intentionally excludes.

### Evidence gaps

Identify anything that cannot currently be observed or verified. Do not disguise assumptions as criteria.

## Rules

- Describe externally meaningful behavior rather than files or algorithms.
- Do not include speculative future requirements.
- Avoid duplicating one requirement under several headings.
- Do not prescribe a new state field, helper, module, or abstraction.
- Prefer a small set of strong acceptance criteria over an exhaustive list of trivial statements.
- Preserve explicit user constraints and previously approved decisions.

## Exit condition

The specification is ready when another reviewer could inspect an implementation and decide whether it satisfies the request without needing to infer the intended behavior.

Do not request approval yet. Continue to implementation planning.
