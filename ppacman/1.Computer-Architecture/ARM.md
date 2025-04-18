# ARM 프로세서 정리

## 프로세서란?

메모리에 저장된 명령어를 실행하는 유한 상태 오토마톤 (Finite State Automaton)

---

## ARM: Advanced RISC Machine

ARM은 "Advanced RISC Machine"의 약자로, 핵심은 RISC 구조에 있다.

### RISC란?

Reduced Instruction Set Computing (감소된 명령 집합 컴퓨팅)

- 복잡한 명령보다 단순한 명령을 빠르게 처리
- 효율적인 작업 수행을 목표로 함

---

## ARM의 구조

ARM은 기본적인 아키텍처만 제공하고, 실제 설계와 최적화는 제조사에 맡긴다.

- 같은 ARM 기반이라도 제조사마다 명령 집합이 다를 수 있음
- 논리 구조는 같지만 서로 다른 칩이 만들어짐

### 명령어와 물리적 구조

- 명령어가 많을수록 칩의 크기와 소비 전력이 증가
- ARM은 명령 집합이 단순해 작고 효율적임

---

## ARM의 장점

- 단순한 명령어 구조 → 적은 트랜지스터 수
- 트랜지스터 수가 적을수록:
  - 전력 소비가 낮고
  - 크기가 작으며
  - 발열도 적음

> 결과적으로 스마트폰, 태블릿, IoT 기기 등에 적합

---

## ARM 생태계의 특징

- ARM용 앱은 ARM 기반 기기에서만 실행됨
- x86 기반 시스템과는 직접 호환되지 않음
  - 호환을 위해선 코드 수정 또는 에뮬레이션 필요

### OS 호환성

- 하나의 ARM OS는 여러 ARM 기기에서 재사용 가능
- 다양한 안드로이드 기기가 나올 수 있는 이유
- iOS는 소스코드 비공개라 제한됨

---

## ARM이 각광받는 이유

- 전력 소모가 적고 크기가 작아 모바일에 적합
- 성능 대비 효율이 뛰어남
- 반도체 제조사들이 꾸준히 구조 개선 중
