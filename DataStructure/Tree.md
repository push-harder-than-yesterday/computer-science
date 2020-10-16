## 트리(Tree)

### 트리(Tree) 란?

- 노드들을 간선으로 연결한 계층형 자료구조로 비선형 자료 구조이다.
  - 최상위 하나의 노드를 루트노드로 하여 나머지 노드들이 간선으로 연결되어 있다.
  - 하나의 노드는 그 자체로 트리이며 루트가 된다.
  - 트리는 사이클(cycle) 이 존재할 수 없다.
  - 그래프의 한 종류이다.
  - 노드가 N개인 트리는 항상 N-1 개의 간선(E, Edge)을 가진다.
  - 임의의 두 노드 간의 경로는 항상 유일하다.
  - 순회는 Pre-order, In-order, Post-order로 이루어진다.
    - 이 3가지 모두 DFS/BFS 안에 있다.
  - 트리는 이진 트리, 이진 탐색 트리, 균형 트리(Red-Black 트리), 이진 힙(최소힙, 최대힙) 등이 있다.
  - e.g. 가족의 족보, 연산 수식, 회사 조직 구조도, 디렉터리 구조 등

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/f/f7/Binary_tree.svg/1920px-Binary_tree.svg.png" width="500">

<p style="text-align: center;">(출처: https://ko.wikipedia.org/wiki/%ED%8A%B8%EB%A6%AC_%EA%B5%AC%EC%A1%B0)</p>

### 트리의 종류

#### 이진 트리(Binary Tree)

- 각 노드가 최대 2개의 자식을 갖는 트리이다.
- 이진 트리의 순회
  - 중위 순회(in-order traversal) : Left -> Root -> Right 순으로 순회
    - 위 그림에서, 2 -> 7 -> 5 -> 6 -> 11 -> 2 -> 4 -> 9 -> 5
  - 전위 순회(pre-order traversal) : Root -> Left -> Right 순으로 순회
    - 위 그림에서, 2 -> 7 -> 2 -> 6 -> 5 -> 11 -> 5 -> 9 -> 4
  - 후위 순회(post-order traversal) : Left -> Right -> Root 순으로 순회
    - 위 그림에서, 2 -> 5 -> 11 -> 6 -> 7 -> 4 -> 9 -> 5 -> 2

#### 완전 이진 트리(Complete Binary Tree)

- 아래 조건을 만족하는 이진 트리를 의미한다.

  > 1. 마지막 레벨을 제외한 나머지 레벨에서는 노드들이 꽉 차있어야 한다.
  > 2. 마지막 레벨은 왼쪽 노드가 채워져있어야 한다.

- 완전 이진 트리는 배열을 사용해 효율적으로 표현이 가능하다.

<img src="https://cdn.programiz.com/sites/tutorial2program/files/complete-binary-tree_0.png" width="350">

<p style="text-align: center;">(출처: https://www.programiz.com/dsa/complete-binary-tree)</p>

#### 정 이진 트리(Full Binary Tree)

- 아래 조건을 만족하는 이진 트리를 의미한다.

  > 1. 루트 노드를 제외한 모든 노드들은 2개의 자식노드를 가지거나 자식 노드가 하나도 없어야 한다.

  <img src="https://cdn.programiz.com/sites/tutorial2program/files/full-binary-tree_0.png" width="350">

  <p style="text-align: center;">(출처: https://www.programiz.com/dsa/full-binary-tree)</p>

#### 포화 이진 트리(Perfect Binary Tree)

- 아래 조건을 만족하는 이진 트리를 의미한다.

  > 1. 모든 노드가 0개 혹은 2개의 자식 노드를 가지며 모든 리프 노드가 똑같은 레벨에 있어야 한다.

- 노드의 갯수는 2^(k-1)개 이다. (k: 트리의 높이)

<img src="https://cdn.programiz.com/sites/tutorial2program/files/perfect-binary-tree_0.png" width="500">

<p style="text-align: center;">(출처: https://www.programiz.com/dsa/perfect-binary-tree)</p>

#### 이진 힙(최소힙과 최대힙)

- 최소힙(Min Heap)
  - 각 노드의 값이 그 자식의 값보다 작거나 같은 트리이면서 완전 이진 트리인 트리를 뜻한다.

- 최대힙(Max Heap)
  - 각 노드의 값이 그 자식의 값보다 크거나 같은 트리이면서 완전 이진 트리인 트리를 뜻한다.

![Min Heap, Max Heap](https://gmlwjd9405.github.io/images/data-structure-heap/types-of-heap.png)

<p style="text-align: center;">(출처: https://gmlwjd9405.github.io/2018/05/10/data-structure-heap.html)</p>

#### 이진 탐색 트리(BST, Binary Search Tree)

- 아래 조건을 만족하는 이진 트리를 의미한다.

  > 1. 이진 탐색 트리의 노드에 저장된 키는 유일하다.
  > 2. 부모의 키가 왼쪽 자식 노드의 키보다 크다.
  > 3. 부모의 키가 오른쪽 자식 노드의 키보다 작다.
  > 4. 왼쪽과 오른쪽 서브 트리도 이진 탐색 트리이다.

- 이진 탐색 트리의 탐색 연산은 **O(logN)의 시간 복잡도** 를 갖는다.

  - 단, 한쪽 방향으로만 데이터가 추가되어 **편향 트리**가 되었을 경우 Worst Case 로 **O(N)의 시간복잡도** 를 갖는다.