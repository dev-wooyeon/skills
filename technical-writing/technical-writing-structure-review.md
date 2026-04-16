<skill>
<name>technical-writing-structure-review</name>
<path>$CODEX_HOME/skills/technical-writing-structure-review/SKILL.md</path>
---
name: technical-writing-structure-review
description: Review and improve the information architecture of a technical document draft or outline. Use when the user provides a draft, table of contents, or rough structure and wants concrete feedback based on single-goal pages, clear overview, predictable hierarchy, value-first introductions, and effective titles.
---

# Technical Writing Structure Review

## Purpose

Analyze a technical document draft or outline, identify structure problems, and
propose one stronger integrated revision. Focus on information architecture,
not sentence-level copyediting.

Typical inputs:

- Full draft
- Table of contents
- Rough outline
- Section list with notes
- Document goal and target reader
- Pain points such as "too much in one page" or "no clear overview"

## Review Principles

Apply these principles in order.

### 1. Cover one goal per page

Check whether the document tries to do too many jobs at once.

Signals of a problem:

- Heading depth reaches `####` or deeper because too many topics are packed in
- Setup, concept explanation, troubleshooting, and API details are mixed
- The page cannot be summarized as one clear reader outcome

Recommended action:

- Narrow the page to one main reader goal
- Split side topics into separate documents when needed
- Keep the current page focused on the dominant task

### 2. Always include an overview

Check whether the opening tells the reader what this document is for.

Signals of a problem:

- The page starts directly with details, commands, or history
- The reader cannot quickly answer "what will I get from this document?"
- The scope, outcome, or intended reader is unclear

Recommended action:

- Add a short overview near the top
- State what the document helps the reader achieve
- Clarify scope, audience, and any key prerequisite if it materially changes
  expectations

### 3. Make the structure predictable

Check whether headings and information order are consistent.

Signals of a problem:

- Sibling headings mix concepts, steps, warnings, and reference entries without
  a pattern
- The document jumps between beginner context and advanced detail
- Terms or heading styles change without reason

Recommended action:

- Reorder from basic context to execution to edge cases
- Keep heading levels and naming patterns consistent
- Use the same terminology for the same concept everywhere

### 4. Deliver value before detail

Check whether the document explains the benefit before configuration or trivia.

Signals of a problem:

- The introduction starts with internals rather than reader outcome
- Secondary details appear before the main value
- The reader must work to discover why the page matters

Recommended action:

- Put user value and expected outcome first
- Move supporting details later unless they block understanding
- Introduce details only after the main promise is clear

### 5. Write effective titles

Check whether the title is searchable, specific, and consistent.

Signals of a problem:

- The title is vague, long, or stylistically inconsistent
- The main keyword is missing
- The title describes a theme rather than the document's job

Recommended action:

- Include the core keyword
- Keep it concise, typically within 30 Korean characters when practical
- Use a consistent style such as noun phrase or plain statement

## Analysis Workflow

Follow this workflow:

1. Identify the document's current main goal.
2. Compare that goal to the actual section mix.
3. Detect structure violations using the five principles.
4. Decide whether the page should stay single or split into multiple documents.
5. Produce one best integrated improvement, not multiple disconnected options.

If the user supplies multiple improvement directions, merge them into one
coherent recommendation.

## What To Produce

Respond in Korean unless the user requests another language.

Always include:

1. `구조 진단`
2. `핵심 문제`
3. `개선 방향`
4. `개선된 문서 구조안`
5. `제목/개요 개선안`

### `구조 진단`

Summarize the document's current state in 2-4 short points.

### `핵심 문제`

Map issues back to the five principles. Be concrete.

Good examples:

- "한 페이지에서 개념 설명과 설정 절차, 에러 대응을 모두 다루고 있어 목표가 분산됩니다."
- "도입부에 개요가 없어 독자가 문서의 기대 결과를 바로 파악하기 어렵습니다."
- "H2는 작업 단계인데 H3는 배경 설명으로 섞여 있어 계층이 예측 가능하지 않습니다."

### `개선 방향`

Explain the restructuring logic:

- what to keep
- what to move
- what to split
- what to bring earlier

Recommend one direction decisively.

### `개선된 문서 구조안`

Provide a concrete revised outline. Prefer this pattern when it fits:

```text
# 제목

## 개요
## 이 문서가 해결하는 문제
## 사전 조건 또는 전제
## 핵심 절차 또는 핵심 개념
## 예외/주의 사항
## 다음에 읽을 문서 또는 관련 문서
```

Adapt the template to the actual document type. For example:

- Tutorial-style pages may use `개요 -> 준비 사항 -> 단계별 진행 -> 다음 단계`
- Troubleshooting pages may use `개요 -> 증상 -> 원인 -> 해결 방법 -> 검증`
- Explanation pages may use `개요 -> 배경 -> 핵심 원리 -> 비교 -> 적용 사례`

### `제목/개요 개선안`

Always provide:

- one improved title
- one sample overview paragraph or 2-3 bullet summary

## Decision Rules for Splitting

Recommend splitting the document when:

- the page serves more than one reader goal
- setup and conceptual explanation are both large enough to stand alone
- troubleshooting is long enough to interrupt the main reading flow
- the heading tree becomes deep because unrelated topics are nested together

When recommending a split, name the proposed child documents explicitly.

## Constraints

- Do not rewrite the entire document unless the user asks
- Focus on architecture, hierarchy, and navigation
- Avoid generic praise
- Tie every major suggestion to a clear reader benefit
- Prefer one polished structure proposal over many shallow alternatives

## Fast Heuristics

- "개요가 없다" -> add overview immediately
- "한 페이지에 설정, 원리, FAQ, API가 다 있다" -> split by reader goal
- "제목이 길고 추상적이다" -> tighten around the core keyword and outcome
- "같은 수준 제목이 서로 다른 역할이다" -> normalize the hierarchy
- "도입부가 구현 세부사항부터 시작한다" -> move value and outcome first

</skill>
