---
name: technical-writing-sentence-polish
description: Improve the clarity, brevity, and consistency of technical writing at the sentence level. Use when the user provides one or more sentences from a technical document and wants direct feedback plus a stronger final rewrite based on concision, reduced meta discourse, concrete wording, consistent terminology, and clear human subjects.
---

# Technical Writing Sentence Polish

## Purpose

Refine technical sentences so they are easier to scan, easier to understand,
and more actionable. Focus on sentence-level improvement, not document
structure or conceptual expansion.

Typical inputs:

- One sentence
- A short paragraph
- A list of awkward technical statements
- Draft prose from a guide, tutorial, design note, or API document

## Core Principles

Apply these five rules in order.

### 1. Keep only necessary information

Make each sentence short and focused.

Check for:

- Sentences that are too long
- Multiple ideas packed into one sentence
- Clauses that do not change the reader's understanding

Recommended action:

- Keep one main idea per sentence
- Split long sentences when needed
- Remove filler that does not add meaning

### 2. Minimize meta discourse

Remove comments about the writing itself when they do not help the reader.

Check for:

- "앞서 설명했듯이"
- "여러분도 아시다시피"
- "다음에서 살펴보겠습니다"
- other phrases that talk around the content instead of delivering it

Recommended action:

- Delete meta framing unless it is needed for navigation
- State the point directly

### 3. Write concretely

Prefer direct, specific wording over vague abstractions.

Check for:

- vague nouns such as "부분", "사항", "과정", "측면"
- weak verbs
- unclear instructions or outcomes

Recommended action:

- replace abstract nouns with concrete objects or actions
- use verbs that show what the reader or system actually does
- name the exact artifact, condition, or action when possible

### 4. Stay consistent

Use the same term for the same concept.

Check for:

- multiple names for one thing
- inconsistent abbreviation handling
- mixed translations or mixed borrowed terms

Recommended action:

- choose one preferred term and use it throughout
- expand abbreviations on first mention if needed
- keep capitalization and spelling stable

### 5. Make the subject clear

Show who acts.

Check for:

- passive voice that hides responsibility
- sentences where the tool or system becomes the subject without reason
- unclear actor in instructions

Recommended action:

- prefer active voice
- make the developer, reader, or operator the subject when giving guidance
- use the system as subject only when system behavior itself matters

## Analysis Workflow

Follow this workflow:

1. Identify the sentence's main intent.
2. Remove extra information or meta phrasing.
3. Rewrite vague wording into concrete language.
4. Normalize terms.
5. Make the subject and action explicit.
6. Return one best final rewrite.

If several fixes are possible, combine them into one polished version instead
of listing many alternatives.

## What To Produce

Respond in Korean unless the user requests another language.

Always include:

1. `문장 진단`
2. `핵심 문제`
3. `수정 방향`
4. `다듬은 문장`

### `문장 진단`

Summarize the sentence quality in 1-3 short points.

### `핵심 문제`

Tie problems back to the five principles.

Good examples:

- "한 문장에 조건과 결과, 주의 사항이 함께 들어 있어 읽는 속도가 떨어집니다."
- "메타 표현이 들어가 핵심 메시지 전달이 늦어집니다."
- "주체가 빠져 있어 누가 무엇을 해야 하는지 바로 드러나지 않습니다."

### `수정 방향`

Explain what changed and why:

- what to delete
- what to split
- which terms to normalize
- how the subject became clearer

### `다듬은 문장`

Return one improved version by default.

When the input is a paragraph, you may return multiple revised sentences, but
still present them as one integrated rewrite.

## Tone Rules

- Prefer plain, direct technical prose
- Avoid decorative transitions
- Avoid vague encouragement or conversational filler
- Keep instructions actionable
- Preserve the original meaning unless the user asks for stronger reframing

## Decision Rules

Split a sentence when:

- it contains more than one main action
- it mixes cause, action, exception, and result in one line
- the condition chain makes the main point hard to find

Keep a sentence as one line when:

- the action and condition are tightly coupled
- splitting would make the flow choppy

## Fast Heuristics

- "정상적으로 응답을 받을 수 있습니다" -> replace with the exact outcome if
  possible
- "포함해야 정상적으로" -> prefer direct action plus result
- long condition chains -> split into setup and result
- passive voice -> rewrite with a clear actor
- mixed terms -> choose one and normalize

## Example Pattern

Input:

```text
이 API를 호출할 때 요청 헤더와 인증 정보를 포함해야 정상적으로 응답을 받을 수 있습니다.
```

Better:

```text
이 API를 호출할 때는 요청 헤더와 인증 정보를 함께 포함하세요. 그래야 서버가 요청을 인증하고 정상 응답을 반환합니다.
```
