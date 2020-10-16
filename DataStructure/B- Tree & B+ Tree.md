## B- Tree & B+ Tree

### B- Tree 란?

**다수의 키**를 가진 노드로 구성되어 다방향 탐색이 가능한 트리이며 대용량 데이터를 위해 고안된 자료구조로서 주로 데이터베이스의 기본 자료구조로 활용되는 트리이다. 

### B- Tree 의 특징

* 루트는 0 또는 2에서 M개 사이의 서브 트리를 가진다.
* 루트 노드와 리프 노드를 제외한 모든 내부 노드는 최소 M/2개, 최대 M개의 서브 트리를 가진다.
* 리프 노드가 아닌 노드에 있는 키 값의 수는 그 노드의 서브 트리 수보다 1개 적다.
* 모든 리프 노드는 같은 레벨이며, 한 노드 안에 있는 키 값들은 오름차순이다.
* 리프 노드는 모두 링크로 연결되어 있다.
* 리프 노드의 키 값의 수는 M/2 이상이다.
* Binary Search Tree와 유사하지만, 한 노드 당 자식 노드가 2개 이상 가능하다.
* 어떤 값에 대해서도 같은 시간에 결과를 얻을 수 있다.
  * 트리 높이가 다른 경우, 약간의 차이는 있지만 O(logN)이라는 시간 복잡도를 구할 수 있다.

![B- Tree](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FqycZ2%2FbtqBQnr4QYG%2F7J8KpnmNaJiTjgS0K9TEIK%2Fimg.png)

<p style="text-align: center;">(출처: https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FqycZ2%2FbtqBQnr4QYG%2F7J8KpnmNaJiTjgS0K9TEIK%2Fimg.png)</p>


### B+ Tree 란?

데이터가 순차적으로 처리되어야 할 때는 트리 구조 내에서 노드 사이를 오르내리는데 많은 처리 시간이 필요하게 되는데 이를 효율적으로 하고자 할 때 B+ Tree를 사용한다.

### B+ Tree 의 특징

* 키에 의해서 각각 식별되는 레코드의 효율적인 삽입, 검색, 삭제를 통해 정렬된 데이터를 표현하기 위한 트리 자료 구조이다.
* B Tree의 변형 구조로 index 부분과 리프 노드로 구성된 순차 데이터 부분으로 이루어진다.
* 인덱스 부분의 key 값은 리프에 있는 key 값을 직접 찾아가는데 사용한다.
* 리프 노드끼리 연결 리스트로 연결되어 있어 범위 탐색에 유리하다.
* B Tree의 경우 Best case에서 루트에서 끝나지만 B+ Tree는 무조건 리프 노드까지 내려가봐야 한다.

![B+ Tree](https://t1.daumcdn.net/cfile/tistory/99051F355B80DB7436)

<p style="text-align: center;">(출처: https://helloino.tistory.com/113)</p>

### B- Tree & B+ Tree 비교

|구분|B- Tree|B+ Tree|
|-------|--------|-------------|
|데이터 저장|리프 노드, 브랜치 노드 모두 데이터 저장 가능|오직 리프 노드에만 데이터 저장 가능|
|트리의 높이|높음|낮음(한 노드 당 key를 많이 담을 수 있음)
|풀 스캔 시, 검색 속도|모든 노드 탐색|리프 노드에서 선형 탐색|
|키 중복|없음|있음(리프 노드에 모든 데이터가 있기 때문)|
|검색|자주 access 되는 노드를 루트 노드 가까이 <br>배치할 수 있고, <br>루트노드에서 가까울 경우 브랜치 노드에도 <br>데이터가 존재하기 때문에 빠름|리프 노드까지 가야 데이터가 존재|

#### 공통점
* 모든 리프 노드의 depth가 같다.
* 각 노드에는 k/2 ~ k개의 자식 노드가 들어있어야 한다.
* 삽입시, overflow가 발생하면 split 한다.
* 삭제시,  underflow가 발생하면 redistribution(복구) 이나 merge(병합) 한다.

#### 차이점
> * B- Tree는 각 노드에 데이터가 저장된다.
> * B+ Tree는 index node와 리프 노드가 분리되어서 존재하며 리프 노드는 서로 연결되어 있어서 임의 접근과 순차 접근 모두 성능이 우수하다.

> * B- Tree의 각 노드에는 key 뿐만 아니라 데이터도 들어갈 수 있으며 여기서 데이터는 disk block으로 pointer가 될 수 있다.
> * B+ Tree는 각 노드에서는 key만 들어가야 한다. 그러므로 B+ Tree 에서 데이터는 오직 리프 노드에만 존재한다.

> * B+ Tree는 삽입, 삭제가 리프 노드에서만 이루어진다.
> * B+ Tree는 리프 노드끼리 `LinkedList` 로 연결되어 있다.