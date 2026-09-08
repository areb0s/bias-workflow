# Implementation Plan

The implementation plan maps the completed specification onto current production code. It remains a proposal until the combined approval.

## Investigate current code

Trace the shortest real path from input to observable output. Confirm graph or search findings against current source before naming a target.

Identify:

- the canonical owner of each affected responsibility;
- current callers, consumers, and state writers/readers;
- nearby production code that is the live reference;
- existing validation seams;
- obsolete code the change should remove.

## Required sections

### Data flow

Show the shortest input → processing → output path before and after the change.

### Ownership

Name exact target files and symbols. Explain what each owner changes and which existing implementation it reuses. State what must not be copied or duplicated.

### State changes

List every state field to add, change, or remove. For each addition, identify its current problem, writer, reader, and why existing state cannot answer the same question. If any answer is missing, omit the field.

### Functions and names

List key functions only when their responsibilities or interfaces change. Prefer domain-role names that read naturally at call sites.

### Removed code

List obsolete render paths, duplicate responsibilities, dead guards, unused exports, or superseded state removed by the change.

### Failure policy placement

Name the single owner of validation, stabilization, retry, fallback, or ambiguity resolution. Downstream code should trust that owner's result.

### Non-goals

Repeat implementation-adjacent exclusions that prevent scope drift.

### Validation

Map each acceptance criterion to focused tests, static checks, builds, or manual evidence. Distinguish existing unrelated failures from regressions caused by the change.

### Expected staging units

When the user requested Git organization or the work naturally spans multiple logical units, describe reviewable staging units. Otherwise omit this section. Do not stage unless the user later requests it.

### Escalation conditions

State discoveries that require returning to concretization, specification, or planning.

## Minimality checks

Before presenting the plan, remove:

- state without a current reader;
- parameters with only one real value;
- one-use wrappers that do not improve clarity;
- duplicate guards or fallbacks;
- future-facing modes or extension points;
- exports without a current external consumer;
- unrelated cleanup.

## Exit condition

The plan is ready when exact targets, ownership, behavior, removals, validation, non-goals, and escalation conditions are explicit enough to implement without inventing a new architectural decision.
