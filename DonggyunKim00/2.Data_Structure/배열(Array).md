# 배열(Array)

### 특징

1. `O(1)`에 k번째 원소를 확인/변경 가능
2. 추가적으로 소모되는 메모리의 양(오버헤드)가 거의 없음
3. Cache hit rate가 높다
4. 메모리 상에 연속한 구간을 잡아야 해서 할당에 제약이 걸린다

### 시간복잡도

1. 임의의 위치에 있는 원소를 확인/변경 → `O(1)`
2. 원소를 끝에 추가 → `O(1)`
3. 마지막 원소를 제거 → `O(1)`
4. 임의의 위치에 원소를 추가/제거 → `O(N)`

### 시간복잡도별 자바스크립트 배열 메서드 정리

#### `O(1)` — 상수 시간

> 배열 길이와 상관없이 일정한 시간 안에 수행됨

| 메서드명                                          |
| ------------------------------------------------- |
| `at()`                                            |
| `entries()`                                       |
| `isArray()`                                       |
| `keys()`                                          |
| `pop()`                                           |
| `push()`                                          |
| `shift()` _(브라우저 구현에 따라 O(n)일 수 있음)_ |
| `values()`                                        |
| `with()`                                          |

#### `O(n)` — 선형 시간

> 배열 전체 또는 일부를 순회

| 메서드명                                  |
| ----------------------------------------- |
| `concat()`                                |
| `copyWithin()`                            |
| `fill()`                                  |
| `filter()`                                |
| `find()`                                  |
| `findIndex()`                             |
| `findLast()`                              |
| `findLastIndex()`                         |
| `flat()`                                  |
| `flatMap()`                               |
| `forEach()`                               |
| `from()`                                  |
| `fromAsync()`                             |
| `group()`                                 |
| `groupToMap()`                            |
| `includes()`                              |
| `indexOf()`                               |
| `join()`                                  |
| `lastIndexOf()`                           |
| `map()`                                   |
| `of()`                                    |
| `reduce()`                                |
| `reduceRight()`                           |
| `reverse()`                               |
| `slice()`                                 |
| `every()`                                 |
| `some()`                                  |
| `splice()` _(삭제/추가 범위에 따라 다름)_ |
| `toLocaleString()`                        |
| `toReversed()`                            |
| `toSpliced()`                             |
| `toString()`                              |
| `unshift()`                               |

### `O(n log n)` — 평균 선형로그 시간

> 정렬 기반 알고리즘 (V8 엔진: TimSort 기반)

| 메서드명     |
| ------------ |
| `sort()`     |
| `toSorted()` |

> `sort()`는 최악의 경우 O(n²)일 수 있음

#### 레퍼런스

- https://velog.io/@pyotato/iterable-object-in-javascript%EC%A0%95%EB%A6%AC-lfmvdw9c
- https://blog.encrypted.gg/927
