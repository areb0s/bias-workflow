# Specification

The specification defines what must be true for the request to be complete. It is a behavioral contract, not an implementation plan.

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
