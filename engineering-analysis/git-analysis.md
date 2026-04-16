# git-analysis

## 역할

git diff, commit history, PR 문안, 리뷰 결과를 저장소의 실제 히스토리에 맞춰
분석하고 정리하는 스킬입니다.

## 언제 쓰는가

- 변경사항을 검토할 때
- staged 또는 unstaged diff를 리뷰할 때
- 커밋 메시지, 브랜치 이름, PR 제목/본문을 쓸 때
- 특정 작성자의 커밋 이력을 요약할 때

## 입력

- 현재 git 상태
- diff 또는 commit history
- 작성하려는 산출물 종류

## 출력

- 리뷰 findings
- commit/PR 초안
- author-based commit report

## 핵심 규칙

- 항상 `git status`, `git diff`, `git log`를 먼저 봅니다.
- 리뷰와 글쓰기 작업을 분리합니다.
- 리뷰는 findings-first로 정리합니다.
- 커밋과 PR 문구는 저장소 히스토리 톤을 따릅니다.

## 관리 포인트

- 사용하는 git 명령과 출력 형식이 현재 워크플로와 맞는지 점검합니다.
- 저장소별 글쓰기 톤을 과도하게 일반화하지 않도록 주의합니다.

## 실행 프롬프트

```text
$git-analysis

작업 유형: <diff 리뷰 / 커밋 메시지 / PR 본문 / 작성자별 커밋 리포트>
대상 범위: <staged / unstaged / 최근 20개 커밋 / 특정 author>
추가 요구: <예: findings-first, 한국어, 저장소 히스토리 톤 반영>

먼저 현재 git 상태와 관련 diff 또는 log를 확인한 뒤,
작업 유형에 맞는 결과를 만들어줘.
검증하지 않은 내용은 추정으로 분리해서 써줘.
```
