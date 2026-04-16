<skill>
<name>tradeoff-decision</name>
<path>$CODEX_HOME/skills/tradeoff-decision/SKILL.md</path>
---
name: tradeoff-decision
description: "Use when comparing technical or structural options and you need a context-aware decision rationale that explains criteria, constraints, risks, and why one choice fits the current situation better than the alternatives."
---

# Trade-off Decision

## 목적
기술이나 구조 선택에서 장단점 비교를 넘어, 어떤 맥락에서 무엇을 선택해야 하는지 판단 근거를 만드는 스킬이다. 아키텍처 리뷰, 면접, 설계 문서에서 매우 자주 사용된다.

## 이 스킬이 필요한 상황
두 개 이상의 선택지를 비교해야 할 때
정답보다 맥락에 맞는 결정을 설명해야 할 때
설계 이유를 문서로 남겨야 할 때

## 핵심 질문
각 선택지의 장점과 한계는 무엇인가
현재 우리 상황에서 더 중요한 기준은 무엇인가
언제 이 선택이 실패할 수 있는가
대안을 버릴 만한 이유는 충분한가

## 입력 데이터
비교 대상 기술 또는 구조
현재 시스템 상황
제약 조건

## 분석 절차
1. 비교 기준을 정의한다.
2. 각 선택지의 장단점을 정리한다.
3. 현재 상황의 제약 조건을 적는다.
4. 가장 중요한 판단 기준을 먼저 정한다.
5. 선택 이유와 비선택 이유를 함께 적는다.

## 산출물 형식
비교 대상
비교 기준
선택지별 장점
선택지별 한계
현재 상황에서의 적합성
최종 선택
선택하지 않은 이유

## 평가 기준
단순 기능 비교가 아니라 의사결정 이유가 보여야 한다.
미래 리스크까지 포함해야 한다.
현재 조직의 현실을 반영해야 한다.

## 프롬프트 템플릿
```text
아래 두 가지 선택지를 현재 상황 기준으로 비교해줘.

다음 형식으로 정리해줘.
1. 비교 기준 정의
2. 각 선택지의 장점과 단점
3. 현재 상황에서 중요한 제약 조건
4. 어떤 상황에서는 A가 맞고 어떤 상황에서는 B가 맞는지
5. 지금 우리 상황에서 더 적합한 선택
6. 그 선택을 했을 때 감수해야 하는 리스크
```

## 활용 예시
Kafka와 AWS IoT Core 비교
ClickHouse와 Redis 비교
모놀리스와 MSA 비교

## 주의할 점
모든 비교에 만능 정답은 없다.
기술 유행보다 문제와 제약이 먼저다.

</skill>
