# Trie (Prefix Tree)

1. Trie란?
   **Trie(트라이)**는 문자열을 저장하고 효율적으로 탐색할 수 있도록 고안된 트리 기반 자료구조이다.
   일반적으로 문자열의 **공통 접두사(prefix)**를 공유하여 메모리를 절약하고 빠른 검색을 제공한다.

다른 이름: Prefix Tree, Digital Tree

2. 예시
   다음과 같은 단어들이 있다고 가정:

```
["apple", "app", "ape", "bat", "bath"]
```

Trie의 구조는 다음과 같이 구성된다:

```
(root)
├── a
│ └── p
│ ├── p (끝) ← "app"
│ │ └── l
│ │ └── e (끝) ← "apple"
│ └── e (끝) ← "ape"
└── b
└── a
└── t (끝) ← "bat"
└── h (끝) ← "bath"
공통된 접두사를 하나의 경로로 표현하여 공간을 절약한다.
```

3. 구조
   Trie의 각 노드는 다음 정보를 가진다:

- 하나의 문자
- 자식 노드 집합 (children)
- 단어의 끝인지 나타내는 불리언 (isEnd)

```
class TrieNode {
children: Record<string, TrieNode>;
isEnd: boolean;

constructor() {
this.children = {};
this.isEnd = false;
}
}
```

4. 주요 연산

- insert(word)
  문자를 하나씩 따라가면서, 노드가 없다면 새로 생성

- 마지막 문자 노드에서 isEnd = true 설정

- search(word)
  정확한 단어가 Trie에 존재하는지 확인

마지막 문자까지 따라가서 isEnd가 true여야 true

- startsWith(prefix)
  해당 접두사로 시작하는 단어가 존재하는지 확인
  isEnd 확인은 필요 없다

5. 장점
   빠른 접두사 기반 검색
   자동완성 기능 구현에 유리
   정렬된 문자열 집합을 빠르게 탐색 가능
   공통 접두사를 공유하여 메모리 절약

6. 단점
   자식 노드를 많이 가지기 때문에 메모리 사용이 많을 수 있음
   문자열 집합이 복잡해질수록 구조가 커짐
   구현이 비교적 복잡함 (특히 유니코드/한글)

7. 활용 사례
   검색어 자동완성
   사전(dictionary) 구현
   문자열 집합 검색
   코딩 테스트 (LeetCode, 백준 등)
