# skills

AI를 활용하며 반복적으로 사용하는 스킬 중 유지 필요가 높은 스킬을
구조화해서 보관하는 저장소입니다.

현재는 두 묶음을 관리합니다.

- `technical-writing/`: 기술 문서 작성 파이프라인
- `engineering-analysis/`: 엔지니어링 분석과 의사결정 보조

## 디렉터리 구조

```text
.
├── README.md
├── technical-writing/
│   ├── technical-writing-pipeline.md
│   ├── technical-writing-type-selector.md
│   ├── technical-writing-structure-review.md
│   └── technical-writing-sentence-polish.md
└── engineering-analysis/
    ├── git-analysis.md
    ├── refactor.md
    ├── double-check.md
    ├── problem-structuring.md
    └── tradeoff-decision.md
```

## Technical Writing

- [technical-writing/technical-writing-pipeline.md](technical-writing/technical-writing-pipeline.md)
  - 문서 유형 결정, 구조 점검, 문장 다듬기를 순서대로 연결하는 상위 스킬
- [technical-writing/technical-writing-type-selector.md](technical-writing/technical-writing-type-selector.md)
  - 학습 중심, 문제 해결, 참조, 설명 중 어떤 문서 유형이 맞는지 판단
- [technical-writing/technical-writing-structure-review.md](technical-writing/technical-writing-structure-review.md)
  - 한 페이지 한 목표, 개요, 예측 가능한 계층 구조를 기준으로 정보 구조 개선
- [technical-writing/technical-writing-sentence-polish.md](technical-writing/technical-writing-sentence-polish.md)
  - 기술 문장을 더 짧고 명확하며 일관되게 다듬는 문장 단위 스킬

## Engineering Analysis

- [engineering-analysis/git-analysis.md](engineering-analysis/git-analysis.md)
  - git diff, commit history, PR 문안, 리뷰 코멘트 작성을 맥락에 맞게 정리
- [engineering-analysis/refactor.md](engineering-analysis/refactor.md)
  - 사용 경로, 경계, 영향도를 먼저 추적한 뒤 리팩터링 순서를 설계
- [engineering-analysis/double-check.md](engineering-analysis/double-check.md)
  - 가장 작은 의미 있는 검증 게이트를 고르고 실행 근거를 명확히 보고
- [engineering-analysis/problem-structuring.md](engineering-analysis/problem-structuring.md)
  - 복잡한 문제를 증상, 원인, 반복 요인, 우선순위로 구조화
- [engineering-analysis/tradeoff-decision.md](engineering-analysis/tradeoff-decision.md)
  - 기술 또는 구조 선택지를 제약 조건과 리스크 기준으로 비교

## 관리 원칙

- 이 저장소는 스킬의 목적, 입력, 출력, 관리 포인트를 빠르게 찾기 위한
  카탈로그입니다.
- 실제 실행 규칙의 원본은 로컬 `~/.codex/skills/<skill-name>/SKILL.md`입니다.
- 스킬의 이름, 역할, 출력 형식이 바뀌면 이 저장소의 대응 문서도 함께
  갱신합니다.
