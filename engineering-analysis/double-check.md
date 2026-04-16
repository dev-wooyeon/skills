---
name: double-check
description: "Use when the task is about execution-based verification: deciding what commands to run, running the smallest meaningful validation gate, summarizing what was confirmed by execution, or explicitly stating what was not run and why."
---

# Verification Gate

This skill handles execution-backed validation for Noah: choose the right gate, run it when feasible, and report confirmed versus unverified status without bluffing.

## When To Use

Use this skill for requests such as:

- "테스트코드 실행해서 확인했어?"
- "검증하고 마무리하자"
- "뭘 돌려야 안전한지 정리해줘"
- "안 돌렸으면 안 돌렸다고 써"
- "최소 검증 게이트로 확인해"

## Core Workflow

1. Choose the smallest meaningful command that validates the requested risk.
2. Run execution-backed checks when feasible.
3. If full validation is expensive, run the highest-signal subset.
4. Report exactly what was confirmed by execution and what remains unverified.

## Reporting Rules

- Distinguish clearly between:
  - confirmed by execution
  - inferred from code inspection
  - not run
- If something was not run, state exactly why.
- Do not collapse partial verification into a full-pass statement.
- Prefer concrete command names over vague statements like "checked" or "verified".

## Gate Selection Rules

- Start with the command most directly tied to the changed risk.
- Escalate to broader validation only when the narrow gate is insufficient.
- If the default suite is untrustworthy, say so and explain the limitation.

## Anti-Patterns

- Do not imply that tests passed when nothing ran.
- Do not run a broad expensive suite first when a narrower gate would answer the question.
- Do not hide verification gaps in summary prose.
