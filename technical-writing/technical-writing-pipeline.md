# technical-writing-pipeline

## 역할

기술 문서를 처음부터 끝까지 다듬는 상위 오케스트레이션 스킬입니다.
문서 유형 결정, 정보 구조 개선, 문장 다듬기 순서로 하위 스킬을 연결합니다.

## 언제 쓰는가

- 문서 방향부터 문장까지 전체 흐름을 잡고 싶을 때
- 아이디어만 있는 상태에서 글쓰기 파이프라인을 시작할 때
- 초안은 있지만 어느 단계부터 손대야 할지 판단이 필요할 때

## 입력

- 문서 목표
- 독자 수준
- 현재 가진 문서 상태
- 지금 가장 필요한 것

## 출력

- 현재 단계 판단
- 추천 진행 순서
- 이번 단계 결과
- 다음 단계 입력 안내

## 핵심 라우팅 규칙

- 아이디어만 있으면 `technical-writing-type-selector`부터 시작합니다.
- 목차나 초안이 있으면 `technical-writing-structure-review`부터 시작합니다.
- 구조가 안정적이고 문장 수정만 필요하면
  `technical-writing-sentence-polish`를 사용합니다.
- 구조 문제로 문장 문제가 반복되면 Step 3에서 Step 2로 되돌립니다.

## 연관 스킬

- `technical-writing-type-selector`
- `technical-writing-structure-review`
- `technical-writing-sentence-polish`

## 관리 포인트

- 하위 스킬 이름이 바뀌면 참조 이름과 기본 프롬프트를 같이 갱신합니다.
- 각 단계의 입력과 출력 정의가 실제 하위 스킬과 일치하는지 주기적으로
  확인합니다.
