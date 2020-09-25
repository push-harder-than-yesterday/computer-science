## Red-Black Tree

### Red-Black Tree 란?

이진 탐색 트리의 Worst case에서 편향 트리가 될 수 있는데 이 때에는 O(N) 만큼의 시간 복잡도를 가지게 된다.
이를 해결하기 위해서 나온 것이 **규형잡힌 이진 검색 트리** 로 대표적인 것이 **Red-Black Tree** 와 **AVL 트리** 이다.
이 중에서 **Red-Black Tree**에 대해 알아본다.

* 이진 탐색 트리(BST)의 일종으로 데이터를 검색, 삽입, 삭제에 균형잡힌 시간 복잡도를 가진 트리이다.

* 검색, 삽입, 삭제 시 시간 복잡도는 O(logN) 이다.

* 아래 조건을 만족하는 이진 탐색 트리를 의미한다.

  > 1. 모든 노드는 **레드** 또는 **블랙** 의 색상을 갖는다.
  > 2. 루트 노드는 **블랙** 이다.
  > 3. 모든 리프 노드(NIL 노드)는 블랙이다.
  >    * 단, 실제 구현에서는 NIL 노드를 포함하지 않고 개념적인 설명을 위해 가상으로 NIL 노드를 사용한다.
  > 4. 레드 노드의 자식들은 전부 블랙이다. (즉, 레드가 중복되지 않는다.)
  > 5. 루트 노드에서 임의의 리프 노드에 이르는 경로에서 만나는 블랙 노드의 수는 모두 같다.

![Red-Black Tree](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=http%3A%2F%2Fcfile28.uf.tistory.com%2Fimage%2F2603643B534D2DFA3AFA8B)

<p style="text-align: center;">(출처: https://itstory.tk/entry/%EB%A0%88%EB%93%9C%EB%B8%94%EB%9E%99-%ED%8A%B8%EB%A6%ACRed-black-tree)</p>

### Red-Black Tree의 삽입(Insert)

8, 18, 5, 15, 17, 25, 40, 80 으로 삽입되는 경우를 예시로 한다.

* 삽입되는 모든 노드의 색깔은 **레드** 로 시작한다.

**Step1 : Insert 8**
![Insert 8](https://nesoy.github.io/assets/posts/20180831/4.png)

(출처: https://nesoy.github.io/articles/2018-08/Algorithm-RedblackTree)

* "루트 노드는 **블랙** 이다." 라는 규칙에 따라 블랙으로 변경된다.

**Step2 : Insert 18**
![Insert 18](https://nesoy.github.io/assets/posts/20180831/5.png)

(출처: https://nesoy.github.io/articles/2018-08/Algorithm-RedblackTree)

**Step3 : Insert 5**
![Insert 5](https://nesoy.github.io/assets/posts/20180831/5.png)

(출처: https://nesoy.github.io/articles/2018-08/Algorithm-RedblackTree)

**Step4 : Insert 15**
![Insert 15](https://nesoy.github.io/assets/posts/20180831/7.png)

(출처: https://nesoy.github.io/articles/2018-08/Algorithm-RedblackTree)

* "**레드** 노드가 연속적으로 올 수 없다." 규칙을 위반되어 **Recoloring 기법** 혹은 **Restructuring 기법** 을 사용하여 해결하여야 한다.
  * Recoloring: 삽입된 노드의 부모의 형제 색깔이 **레드** 인 경우
  * Restructuring: 삽입된 노드의 부모의 형제 색깔이 **블랙** 인 경우, NULL 인 경우
* 위 케이스에서는 15 노드의 부모의 형제 색깔이 **레드** 이기 때문에 **Recoloring** 을 통해 해결한다.
  * 삽입된 노드의 부모와 부모 형제 노드를 **블랙** 으로, 부모의 부모노드를 **레드** 로 Coloring 한다.
  * 부모의 부모노드가 루트 노드인 경우 "루트 노드는 **블랙**이다." 조건에 맞게 **블랙** 을 유지한다.

**Step5 : Insert 17**
![Insert 17](https://nesoy.github.io/assets/posts/20180831/8.png)

(출처: https://nesoy.github.io/articles/2018-08/Algorithm-RedblackTree)

* 삽입된 노드의 부모의 형제 색깔이 NULL 이기 때문에 **Restructuring** 을 통해 해결한다.
  * 삽입된 노드, 부모, 부모의 부모를 오름차순으로 정렬한다.
  * 중앙 값을 부모 노드로 만들고 나머지 노드를 자식으로 변환한다.
  * 부모 노드가 된 노드를 **블랙**, 나머지 노드들을 **레드** 로 Coloring 한다.

**Step6 : Insert 25**
![Insert 25](https://nesoy.github.io/assets/posts/20180831/9.png)

(출처: https://nesoy.github.io/articles/2018-08/Algorithm-RedblackTree)

* "**레드** 노드가 연속적으로 나올 수 없다." 규칙을 위반하였고 삽입된 노드의 부모의 형제 노드가 **레드**인 경우에 해당하여 **Recoloring** 을 통해 해결한다.
  * 삽입된 노드의 부모와 부모 형제 노드를 **블랙** 으로, 부모의 부모 노드를 **레드** 로 Coloring 한다.

**Step7 : Insert 40**
![Insert 40](https://nesoy.github.io/assets/posts/20180831/10.png)



* 삽입된 노드의 부모의 형제 색깔이 NULL 이기 때문에 **Restructuring** 으로 해결한다.
  * 삽입된 노드, 부모, 부모의 부모 노드를 오름차순으로 정렬한다.
  * 중앙 값을 부모 노드로 만들고 나머지를 자식 노드로 변환한다.
  * 부모 노드가 된 노드를 **블랙** 으로, 나머지 노드를 **레드** 로 Coloring 한다.

**Step8 : Insert 80**
![Insert 80](https://nesoy.github.io/assets/posts/20180831/11.png)

(출처: https://nesoy.github.io/articles/2018-08/Algorithm-RedblackTree)

* "**레드** 노드가 연속적으로 나올 수 없다" 규칙을 위배했고 삽입된 노드의 부모의 형제 색깔이 **레드** 인 경우에 속해 **Recoloring** 으로 해결한다.

  * 삽입된 노드의 부모와 부모 형제 노드를 **블랙** 으로, 부모의 부모 노드를 **레드** 로 Coloring 한다.

* 그 이후에도 Double Red가 발생하게 되고 25 노드의 형제 색깔이 **블랙**이기 때문에 **Restructuring** 으로 해결한다.

  * 삽입된 노드, 부모, 부모의 부모 노드를 오름차순으로 정렬한다.

  * 중앙 값을 부모 노드로 만들고 나머지 노드를 자식으로 변환한다.

  * 부모 노드가 된 노드를 **블랙** 으로, 나머지 노드를 **레드** 로 Coloring 한다.

    > Step8 의 마지막 그래프에서 노드 10은 오타로 노드 8이 맞다.

### Red-Black Tree의 삭제(Remove)

* **블랙** 노드를 삭제할 때에 삭제 연산으로 Red-Black Tree의 특성이 깨지지 않도록 해야 한다.
* 삽입 때 고려했던 것과 유사한 방식으로 **rotation** 을 구현함으로써 해결할 수 있다.
* **레드** 노드를 삭제하는 경우 그냥 삭제하면 된다.

### Red-Black Tree의 복잡도(Complexity)

| Algorithm | Average | Worst case |
| --------- | ------- | ---------- |
| Space     | O(N)    | O(N)       |
| Search    | O(logN) | O(logN)    |
| Insert    | O(logN) | O(logN)    |
| Delete    | O(logN) | O(logN)    |

