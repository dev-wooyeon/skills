---
name: technical-writing-pipeline
description: Orchestrate a multi-step technical writing workflow from document type selection to information architecture review and sentence polishing. Use when the user is planning, drafting, or refining a technical document and wants the right sub-skill applied in the right order instead of handling each step manually.
---

# Technical Writing Pipeline

## Purpose

Guide a technical document through the full writing pipeline:

1. choose the right document type
2. improve the information architecture
3. polish the sentences

Use this skill as the top-level router when the user wants help with the whole
writing process, not just one isolated step.

This skill coordinates these child skills:

- `$technical-writing-type-selector`
- `$technical-writing-structure-review`
- `$technical-writing-sentence-polish`

## When To Use This Skill

Use this pipeline when the user says things like:

- "기술 문서를 처음부터 잘 쓰고 싶다"
- "이 초안을 어떤 문서 유형으로 써야 할지부터 다듬고 싶다"
- "문서 방향, 구조, 문장까지 순서대로 정리하고 싶다"
- "글쓰기 파이프라인으로 묶고 싶다"

Do not use this skill when the user clearly wants only one step. In that case,
use the specific child skill directly.

## Workflow

Run the workflow in this order unless the user's current state allows you to
skip earlier steps.

### Step 1. Choose the document type

Use `$technical-writing-type-selector` when the user is still deciding what kind of
document to write.

Input to gather:

- document goal
- audience level
- project context
- extra constraints

Expected output:

- one primary documentation type
- optional secondary type only if necessary
- type-specific writing guidance

Skip Step 1 only when the document type is already fixed and explicit.

### Step 2. Review the structure

Use `$technical-writing-structure-review` when the user has an outline, draft, or table
of contents and wants to improve information architecture.

Input to gather:

- current draft or structure
- optional document goal and audience
- current pain points

Expected output:

- structure diagnosis
- key structural issues
- one improved outline
- better title and overview proposal

Skip Step 2 only when the user is asking strictly for sentence-level cleanup of
already-final structure.

### Step 3. Polish the sentences

Use `$technical-writing-sentence-polish` when the structure is acceptable and the user
needs clearer, shorter, more consistent prose.

Input to gather:

- one sentence
- a short paragraph
- selected parts of the draft

Expected output:

- sentence diagnosis
- key issues
- editing direction
- one improved rewrite

## State-Based Routing

Choose the starting step based on the user's material.

- The user has only an idea or topic:
  start at Step 1
- The user already knows the document type and has a rough outline:
  start at Step 2
- The user has a stable draft and asks for phrasing help:
  start at Step 3
- The user asks for end-to-end help:
  run Steps 1 -> 2 -> 3

## Pipeline Rules

- Prefer one clear recommendation at each stage
- Do not dump generic checklists without applying them to the user's context
- Preserve decisions from earlier steps unless the later material proves they
  were wrong
- If Step 2 reveals that the chosen type is wrong, explicitly revisit Step 1
- If Step 3 reveals repeated sentence problems caused by structure, send the
  user back to Step 2 instead of over-editing locally

## Handoff Rules Between Steps

When moving from one step to the next, carry forward only the minimum useful
context.

From Step 1 to Step 2, carry:

- chosen primary document type
- target reader
- writing goal
- known constraints

From Step 2 to Step 3, carry:

- revised section structure
- preferred terminology
- title and overview direction

Do not restate the whole earlier analysis unless it is necessary for the next
step.

## Response Strategy

When using this pipeline directly, respond in Korean unless the user requests
another language.

If the user wants the full pipeline, structure the response like this:

1. `현재 단계 판단`
2. `추천 진행 순서`
3. `이번 단계 결과`
4. `다음 단계 입력 안내`

### `현재 단계 판단`

State where the user currently is in the pipeline.

Examples:

- "지금 상태에서는 문서 유형이 아직 고정되지 않아 Step 1부터 시작하는 편이 맞습니다."
- "문서 유형은 이미 정해졌고 목차가 있으므로 Step 2부터 시작하면 됩니다."

### `추천 진행 순서`

Show the full path briefly, even if only one step will be executed now.

Examples:

- "Step 1에서 문서 유형을 정한 뒤, Step 2에서 목차를 정리하고, 마지막으로 Step 3에서 문장을 다듬는 흐름이 적절합니다."
- "이번 요청은 Step 3만 수행해도 충분합니다."

### `이번 단계 결과`

Provide the actual analysis or recommendation from the current step.

### `다음 단계 입력 안내`

Tell the user exactly what to provide next.

Examples:

- "다음 단계로 가려면 현재 목차나 초안을 보내 주세요."
- "문장 다듬기로 넘어가려면 수정하고 싶은 문단만 추려서 보내 주세요."

## Escalation Rules

Recommend splitting the work when:

- the document type is still ambiguous
- the draft mixes multiple reader goals
- the user asks for sentence polish on a structurally unstable draft

In those cases, do not pretend later-stage editing is enough.

## Fast Heuristics

- topic only -> Step 1
- outline or TOC -> Step 2
- paragraph or sentence edits -> Step 3
- "처음부터 끝까지" -> full pipeline
- "문장만 다듬어 줘" -> Step 3 only
- "문서 방향이 맞는지 모르겠다" -> Step 1, then possibly Step 2
