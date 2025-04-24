# 힙(Heap)

> **완전 이진 트리의 일종**으로 여러 값 중, 최대값과 최소값을 빠르게 찾아내도록 만들어진 자료구조
> **우선순위 큐**를 위해서 만들어진 자료구조

```ABAP
❓ 우선순위 큐 ❓

- 우선순위 큐: 우선순위의 개념을 큐에 도입한 자료 구조
- 데이터들이 우선순위를 가지고 있고 우선순위가 높은 데이터가 먼저 나간다.
- 우선순위 큐는 배열, 연결리스트, 힙 으로 구현이 가능하다. 이 중에서 힙(heap)으로 구현하는 것이 가장 효율적이다.
  (삽입, 삭제가 모두 OlogN 이기 때문)

📌 우선순위 큐의 이용 사례

- 시뮬레이션 시스템
- 네트워크 트래픽 제어
- 운영 체제에서의 작업 스케쥴링
- 수치 해석적인 계산
```

### 성질

```ABAP
1. 힙은 일종의 반정렬 상태(느슨한 정렬 상태) 를 유지한다.
  - 큰 값이 상위 레벨에 있고 작은 값이 하위 레벨에 있다는 정도
  - 간단히 말하면 부모 노드의 키 값이 자식 노드의 키 값보다 항상 큰(작은) 이진 트리를 말한다.
2. 힙 트리에서는 중복된 값을 허용한다. (이진 탐색 트리에서는 중복된 값을 허용하지 않는다.)
3. 요소의 삽입/삭제 연산이 O㏒N 이다. (heapify의 과정의 시간복잡도가 O㏒N 임)
```

### 힙의 종류

<img src='https://t1.daumcdn.net/cfile/tistory/17084F504DA9895214'>

- 최대 힙 (max heap): 부모 노드의 키 값이 자식 노드의 키 값보다 크거나 같은 완전 이진 트리
- 최소 힙 (min heap): 부모 노드의 키 값이 자식 노드의 키 값보다 작거나 같은 완전 이진 트리

### 구현

```ABAP
💡 Tip

- 힙을 저장하는 표준적인 자료구조는 배열이다.
- 특정 위치의 노드 번호는 새로운 노드가 추가되어도 변하지 않는다.

- 힙에서의 부모 노드와 자식 노드의 관계
  - 왼쪽 자식의 인덱스 = (부모의 인덱스) * 2
  - 오른쪽 자식의 인덱스 = (부모의 인덱스) * 2 + 1
  - 부모의 인덱스 = (자식의 인덱스) / 2

- 힙의 요소 추가 과정
  1. 배열의 끝에 요소 push
  2. heapifyUp 과정을 통해 부모노드와 비교하며 자리를 찾아감

- 힙의 요소 삭제 과정
  1. 가장 앞쪽의 노드에 마지막 노드를 삽입
  2. heapifyDown 과정을 통해 자식 노드와 비교하며 자리를 찾아감
```

```javascript
// 최대 힙 구현 예제
class MaxHeap {
  constructor() {
    this.heap = [];
  }

  insert(value) {
    this.heap.push(value);
    this._heapifyUp();
  }

  extractMax() {
    if (this.size() === 0) return undefined;
    if (this.size() === 1) return this.heap.pop();

    const max = this.heap[0];
    this.heap[0] = this.heap.pop(); // 마지막 원소를 루트로 올림
    this._heapifyDown();
    return max;
  }

  peek() {
    return this.heap[0];
  }

  size() {
    return this.heap.length;
  }

  _heapifyUp() {
    let index = this.heap.length - 1;
    while (index > 0) {
      const parent = Math.floor((index - 1) / 2);
      if (this.heap[parent] >= this.heap[index]) break;

      [this.heap[parent], this.heap[index]] = [
        this.heap[index],
        this.heap[parent],
      ];

      index = parent;
    }
  }

  _heapifyDown() {
    let index = 0;
    const length = this.heap.length;

    while (true) {
      const left = 2 * index + 1; // 왼쪽 자식 요소의 idx
      const right = 2 * index + 2; // 오른쪽 자식 요소의 idx
      let largest = index;

      if (left < length && this.heap[left] > this.heap[largest]) {
        largest = left;
      }

      if (right < length && this.heap[right] > this.heap[largest]) {
        largest = right;
      }

      if (largest === index) break;

      [this.heap[largest], this.heap[index]] = [
        this.heap[index],
        this.heap[largest],
      ];

      index = largest;
    }
  }
}
```

#### 레퍼런스

- https://gmlwjd9405.github.io/2018/05/10/data-structure-heap.html
- https://gyoogle.dev/blog/computer-science/data-structure/Heap.html
