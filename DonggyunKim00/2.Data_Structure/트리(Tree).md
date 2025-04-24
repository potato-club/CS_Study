# 트리(Tree)

> 노드와 간선으로 이루어진 자료구조

<img src='https://www.geeksforgeeks.org/wp-content/uploads/binary-tree-to-DLL.png'>

```ABAP
1. 값을 가진 노드(Node)와 노드를 연결하는 간선(Edge)으로 이루어져있다.
2. 그림 상 데이터 1을 가진 노드가 루트(Root) 노드
3. 모든 노드들은 0개 이상의 자식 노드를 갖고있으며 보통 부모-자식 관계로 부름
```

### 성질

```ABAP
- 트리에는 사이클이 존재할 수 없음! (사이클이 만들어진다면 트리가 아닌 그래프)
- 모든 노드는 자료형으로 표현 가능
- 루트에서 한 노드로 가는 경로는 유일함
- 노드의 개수가 N개면, 간선은 N-1개
```

### 트리 순회 방식

<img src='https://www.techiedelight.com/wp-content/uploads/Print-Binary-Tree-1.png'>

#### 1. Pre-Order

> Root → 왼쪽 자식 → 오른쪽 자식

```
1 → 2 → 4 → 3 → 5 → 7 → 8 → 6
```

#### 2. In-Order

> 왼쪽 자식 → Root → 오른쪽 자식

```
4 → 2 → 1 → 7 → 5 → 8 → 3 → 6
```

#### 3. Post-Order

> 왼쪽 자식 → 오른쪽 자식 → Root

```
4 → 2 → 7 → 8 → 5 → 6 → 3 → 1
```

#### 4. Level-Order

> 루트부터 계층 별로 방문

```
1 → 2 → 3 → 4 → 5 → 6 → 7 → 8
```
