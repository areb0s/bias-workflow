# Concretization

Concretization turns a request into an understood problem and boundary. It does not choose implementation details.

## Investigate first

Before asking the user:

1. Read applicable project instructions.
2. Inspect current behavior, nearby production code, canonical owners, callers, and consumers.
3. Check prior approved decisions and durable project constraints when available.
4. Separate observed facts from assumptions.
5. Answer from evidence anything that does not require user judgment.

Keep this stage read-only.

## Clarify one decision at a time

Ask only the most fundamental unresolved question, preferring this order:

1. Desired user-visible behavior
2. Source of truth
3. Responsibility owner
4. Acceptable failure, omission, delay, or fallback
5. Explicitly excluded scope
6. Implementation detail that current code cannot determine

Use this shape:

```markdown
## 현재 상태
구체화 중

## 확인된 사실
- Evidence-backed facts

## 남은 결정
- The single unresolved choice

## 질문
- One neutral, concrete question
```

Do not batch hypothetical questions. Offer options only when they clarify a real trade-off.

## Exit condition

Concretization is complete when the desired result, affected actors, preserved behavior, change boundary, and material ambiguity can be explained without relying on an implementation proposal.

Its output should capture:

- purpose;
- current problem;
- desired observable change;
- preserved behavior;
- in-scope boundary;
- known non-goals;
- unresolved decisions, which must be empty before specification.
