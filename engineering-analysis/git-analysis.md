---
name: git-analysis
description: "Use when the task is centered on git history or changes: staged or unstaged diff review, recent commit analysis, author-filtered commit reports, commit message or branch name suggestion, PR title or PR body drafting, or repo-history-aligned wording for engineering artifacts."
---

# Git Change Analysis

This skill handles git-centric analysis and writing for Noah: diff review, commit and PR wording, and repo-history-aware change summaries.

## When To Use

Use this skill for requests such as:

- "git changes 확인하고 리뷰하자"
- "변경사항 봐줘"
- "staged diff 리뷰해"
- "$git-analysis 지난 커밋 이력을 확인해서 user.name eunwoo.park이 기여한 커밋 리포트를 제공해"
- "커밋 메시지 추천해줘"
- "git log 보고 커밋 문구 맞춰줘"
- "PR 본문 작성해줘"
- "PR 본문 히스토리 톤에 맞게 써줘"

## Core Workflow

Before answering, inspect local git context first:

- `git status --short --branch`
- `git diff --staged` or `git diff`
- `git log --oneline -n 15`

Then:

1. Separate code review from writing work.
2. For review, default to findings-first output.
3. For commit or PR text, mirror repo history instead of imposing generic conventions.
4. Default to Korean for internal engineering writing unless the repo is clearly English-first.
5. Separate observed facts from assumptions.
6. Never imply validation that was not executed.

## Commit History Report Rules

When the user asks for a commit report, contribution summary, or author-based history analysis:

- Identify whether the filter is based on `user.name`, author name, or author email.
- Use git history commands that preserve evidence, such as author-filtered `git log` views.
- Summarize both volume and substance:
  - commit count and date range
  - dominant areas or files touched
  - notable themes or recurring work types
  - representative commits worth highlighting
- If the requested identity is ambiguous, say what exact filter was used.
- Keep the report factual. Do not overstate impact beyond what the commit history supports.

## Review Rules

- Read surrounding code, not only the diff.
- Prioritize broken behavior, validation gaps, contract leaks, flaky tests, and regression risk.
- Present findings first, ordered by severity.
- Use absolute file references when possible.
- Keep summaries brief and only after the findings.

## Writing Rules

When drafting commit or PR text:

- Inspect `git log` before writing.
- Keep the tone formal and reviewer-friendly.
- For PR bodies, prefer:
  - 목표
  - 변경사항
  - 의도 또는 선택 이유
  - 테스트 근거
  - 리스크

## Anti-Patterns

- Do not write commit or PR text before checking repo history.
- Do not give a review that is mostly summary.
- Do not claim tests passed unless they were actually run.
