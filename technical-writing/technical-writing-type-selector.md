---
name: technical-writing-type-selector
description: Choose the best documentation type and writing approach for a technical writing task. Use when the user wants to decide whether a document should be learning-oriented, problem-solving, reference, or explanatory, or when they need guidance on how to write the chosen type based on goal, audience, project context, and extra constraints.
---

# Technical Writing Type Selector

## Purpose

Infer the single best primary documentation type from the user's situation,
then explain how to write it well. Prefer one primary type. Recommend a
secondary type only when the document has two clearly separate jobs.

Use these four types:

- `학습 중심`: teach by guided practice
- `문제 해결`: help someone complete a task or fix a problem now
- `참조`: help someone look up exact facts quickly
- `설명`: help someone deeply understand concepts, tradeoffs, and rationale

## Required Inputs

Base the recommendation on:

- 문서 목표
- 독자 수준
- 프로젝트 상황
- 추가 고려 사항

If one field is missing, infer cautiously from the others and state the
assumption. Ask a follow-up question only if the choice is genuinely blocked.

## Decision Rules

Choose in this order:

1. Determine the user's dominant intent.
2. Adjust for reader experience and urgency.
3. Pick one primary type.
4. Add one secondary type only if the document must serve both onboarding and
   operational needs, or both conceptual understanding and day-to-day lookup.

### 1. Pick by dominant intent

- The reader must learn step by step and build skill from zero:
  `학습 중심`
- The reader must solve an error, ship a setup, or finish a task quickly:
  `문제 해결`
- The reader already knows the area and mainly needs syntax, options, limits,
  or exact behavior:
  `참조`
- The reader must understand why the technology exists, how it works, and how
  it compares to alternatives:
  `설명`

### 2. Adjust for reader level

- 초급 독자: bias toward `학습 중심` unless the request is clearly operational
  troubleshooting
- 중급 이상 독자 with immediate execution needs: bias toward `문제 해결`
- 숙련 독자 who revisit details repeatedly: bias toward `참조`
- Readers making architectural or conceptual decisions: bias toward `설명`

### 3. Adjust for project context

- 새 기술 도입, 팀 온보딩, 체계적 학습: favor `학습 중심`
- 기존 시스템 개선, 장애 대응, 빠른 적용: favor `문제 해결`
- 문서가 길고 찾기 어려움, 반복 조회가 많음: favor `참조`
- 기술 선택 이유 정리, 공통 이해 형성, 원리 설명 필요: favor `설명`

### 4. When to allow a hybrid

Use a hybrid only when a single document would otherwise fail its job.

- `설명 + 학습 중심`: concept-heavy onboarding
- `문제 해결 + 참조`: operational guide plus exact command or option lookup
- `학습 중심 + 참조`: tutorial plus appendix for repeated reuse

Avoid weak hybrids like "everything at once." If the content genuinely has two
jobs, recommend splitting it into two documents.

## Writing Guidance by Type

### `학습 중심`

Use when the goal is capability building, not just information delivery.

Must include:

1. Clear learning goal and what the reader can do afterward
2. Prerequisites and environment setup
3. Step-by-step flow with both "what" and "why"
4. Runnable examples that grow in difficulty
5. FAQ or common mistakes at the end

Watch for:

- Do not assume missing background knowledge
- Keep each step executable without hidden context
- Validate that examples actually run
- Prevent abrupt difficulty jumps

### `문제 해결`

Use when the reader needs a practical result immediately.

Must include:

1. Precise problem statement or task goal
2. Root cause or required background
3. Ordered solution steps
4. Runnable commands or code
5. Environment differences such as OS, version, or library behavior
6. Why the fix works

Watch for:

- Put the fastest safe path near the top
- Distinguish symptoms from causes
- Call out version-specific differences explicitly
- Remove conceptual detours that delay execution

### `참조`

Use when the reader needs exact facts fast.

Must include:

1. Short overview
2. Syntax and parameter definitions with type, default, and required status
3. Return values and types
4. Examples from basic to advanced
5. Related APIs, functions, or components
6. Warnings and limits

Watch for:

- Optimize for scanning, not storytelling
- Keep naming, ordering, and formatting consistent
- Avoid hiding critical constraints in prose
- Make lookup sections independently useful

### `설명`

Use when the reader needs mental models and technical judgment.

Must include:

1. Historical background and the problem the concept solves
2. Core principles and mechanism
3. Comparison with alternatives and tradeoffs
4. Diagrams or other visual aids when helpful
5. Real use cases and applications

Watch for:

- Do not collapse into API usage notes
- Separate principle from implementation detail
- Show tradeoffs, not just benefits
- Use examples to reinforce theory rather than replace it

## Response Format

Respond in Korean unless the user requests another language. Do not use emoji.

Use this structure:

1. `추천 문서 유형`: choose one primary type
2. `추천 이유`: connect the choice to goal, reader, project context, and extra
   considerations
3. `보조 유형`: include only if necessary, otherwise omit
4. `작성 시 유의할 점`: give concrete guidance tailored to the chosen type
5. `문서 구성 제안`: suggest a practical section outline

## Output Style Rules

- Prefer a firm recommendation over a vague list
- If two types are close, explain why one should lead
- Tailor the advice to the provided context instead of dumping generic checklists
- Be explicit about assumptions
- If the user appears to be designing a writing workflow, mention whether this
  document should remain a single artifact or be split into separate docs

## Fast Heuristics

- "처음 배우는 사람에게 React Hook를 이해시키고 싶다":
  primary `설명`, secondary `학습 중심`
- "Webpack 설정을 바로 잡게 하고 싶다":
  primary `문제 해결`
- "옵션과 반환 타입을 빨리 찾게 하고 싶다":
  primary `참조`
- "왜 이 아키텍처를 선택했는지 설득하고 싶다":
  primary `설명`
- "신입이 따라 하며 환경을 세팅하게 하고 싶다":
  primary `학습 중심`

## Prompt Template

Use this when the user wants a direct, reusable prompt:

```text
$technical-writing-type-selector

문서 목표: <예: React Hook의 개념을 이해시키고 싶다>
독자 수준: <예: React를 처음 접하는 초급 개발자>
프로젝트 상황: <예: 새 기술 온보딩 문서를 만들고 있다>
추가 고려 사항: <예: 짧은 시간 안에 초안을 완성해야 한다>

위 정보를 바탕으로
1. 가장 적합한 주 문서 유형을 하나 고르고
2. 왜 그 유형이 맞는지 설명하고
3. 필요하면 보조 유형을 하나만 제안하고
4. 그 유형에 맞는 작성 시 유의점과 권장 문서 구성을 제안해줘.
```
