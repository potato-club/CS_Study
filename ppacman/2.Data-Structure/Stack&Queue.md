# Stack

> LIFO (Last In, First Out) : 나중에 들어온 데이터가 먼저 나간다

**주요 연산**

```text
push(value): 데이터 추가 (맨 위에)
pop(): 데이터 제거 (맨 위에서 꺼냄)
peek() 또는 top: 가장 위에 있는 데이터 확인 (제거 X)
```

## 사용 예시

- 웹 브라우저 뒤로가기 버튼
- 재귀함수(스택 프레임)
- 괄호 검사 문제
- DFS(길이 우선 탐색)

# Queue

> FIFO (First In First Out) : 먼저 들어온 데이터가 먼저 나간다.

**주요 연산**

```text
enqueue(value): 데이터 추가 (뒤에)
dequeue(): 데이터 제거 (앞에서 꺼냄)
peek() 또는 front: 가장 앞에 있는 데이터 확인
```

## 사용예시

- 대기열 시스템 (은행, 콜센터 등)
- BFS(너비 우선 탐색)
- 프린터 작업 큐
- 캐시 (LRU 알고리즘)
