# 트라이(Trie)

> 문자열에서 검색을 빠르게 도와주는 트리 형태의 자료구조
> 자동완성, 사전 검색 등 문자열을 탐색하는데 특화되어 있음

다음 그림은 문자열 집합 {"rebro", "replay", "hi" , "high", "algo"} 를 트라이로 구현한 것

<img src='https://images.velog.io/images/klloo/post/ec2b6abb-c725-41cd-af6e-046a9ef5f000/image.png'>

- 한 문자열에서 다음에 나오는 문자가 현재 문자의 자식 노드가됨
- 빨간색으로 나타낸 리프노드는 문자열의 끝을 의미함
- 문자열의 추가와 탐색이 모두 O(M)만에 가능

#### 레퍼런스

- https://velog.io/@klloo/%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0-%ED%8A%B8%EB%9D%BC%EC%9D%B4Trie-%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0
