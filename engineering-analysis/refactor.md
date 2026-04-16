---
name: refactor
description: "Use when the task is about refactoring or structural cleanup: usage-path tracing, impact analysis, DDD or MSA boundary critique, external contract mapping, anti-corruption layer decisions, refactor sequencing, or migration and cleanup roadmaps."
---

# Refactor Workflow

This skill handles structural analysis and refactoring strategy for Noah: trace where things are used, find coupling, critique boundaries, and turn cleanup into an executable sequence.

## When To Use

Use this skill for requests such as:

- "어디서 사용하는지 찾아"
- "호출 경로 파악해"
- "영향 분석해"
- "이 구조가 DDD/MSA 관점에서 맞나?"
- "외부 API 계약이 내부 모델에 새는지 봐줘"
- "정리 로드맵 작성하자"
- "마이그레이션 순서 짜자"

## Core Workflow

1. Trace the current structure before proposing a refactor.
2. Distinguish confirmed usage paths from likely usage paths.
3. Evaluate ownership boundaries before implementation convenience.
4. Identify where internal schema semantics leak into DTOs, status codes, events, or APIs.
5. Turn conclusions into a concrete order of work.

## Trace And Impact Rules

- Prefer real call paths over grep dumps.
- Identify entry points, downstream consumers, persistence boundaries, and external contract surfaces.
- Summarize impact so it can become a checklist or refactor plan.

## Architecture Rules

- Check whether the boundary owns the translation or merely renames leaked internals.
- Prefer anti-corruption or translation layers when they preserve ownership clarity.
- Call out hidden coupling across domains, services, or teams.
- Frame tradeoffs in migration cost, responsibility separation, and future architecture constraints.
- Avoid drifting into code changes unless the user asks for implementation options.

## Planning Rules

- Sequence by dependency and risk reduction.
- Prefer a plan that can be executed commit by commit.
- For legacy cleanup, separate:
  - discovery
  - isolation
  - migration
  - verification

## Anti-Patterns

- Do not approve a design just because it is faster to ship.
- Do not give a refactor plan without tracing current usage first.
- Do not blur confirmed findings with assumptions.
