# 자료 구조

### **목차**

- [그래프(Graph)](https://github.com/TaeHyungK/computer-science/blob/master/DataStructure/%EA%B7%B8%EB%9E%98%ED%94%84.md#%EA%B7%B8%EB%9E%98%ED%94%84graph)
  - [그래프(Graph) 란?](https://github.com/TaeHyungK/computer-science/blob/master/DataStructure/%EA%B7%B8%EB%9E%98%ED%94%84.md#%EA%B7%B8%EB%9E%98%ED%94%84graph-%EB%9E%80-)
  - [그래프의 종류](https://github.com/TaeHyungK/computer-science/blob/master/DataStructure/%EA%B7%B8%EB%9E%98%ED%94%84.md#%EA%B7%B8%EB%9E%98%ED%94%84%EC%9D%98-%EC%A2%85%EB%A5%98)
  - [그래프의 탐색](https://github.com/TaeHyungK/computer-science/blob/master/DataStructure/%EA%B7%B8%EB%9E%98%ED%94%84.md#%EA%B7%B8%EB%9E%98%ED%94%84%EC%9D%98-%ED%83%90%EC%83%89)
- [트리(Tree)](https://github.com/TaeHyungK/computer-science/blob/master/DataStructure/%ED%8A%B8%EB%A6%AC.md#%ED%8A%B8%EB%A6%ACtree)
  - [트리(Tree) 란?](https://github.com/TaeHyungK/computer-science/blob/master/DataStructure/%ED%8A%B8%EB%A6%AC.md#%ED%8A%B8%EB%A6%ACtree-%EB%9E%80)
  - [트리의 종류](https://github.com/TaeHyungK/computer-science/blob/master/DataStructure/%ED%8A%B8%EB%A6%AC.md#%ED%8A%B8%EB%A6%AC%EC%9D%98-%EC%A2%85%EB%A5%98)
- [Red-Black Tree](https://github.com/TaeHyungK/computer-science/blob/master/DataStructure/Red-Black%20Tree.md#red-black-tree)
  - [Red-Black Tree 란?](https://github.com/TaeHyungK/computer-science/blob/master/DataStructure/Red-Black%20Tree.md#red-black-tree-%EB%9E%80)
  - [Red-Black Tree의 삽입(Insert)](https://github.com/TaeHyungK/computer-science/blob/master/DataStructure/Red-Black%20Tree.md#red-black-tree%EC%9D%98-%EC%82%BD%EC%9E%85insert)
  - [Red-Black Tree의 삭제(Remove)](https://github.com/TaeHyungK/computer-science/blob/master/DataStructure/Red-Black%20Tree.md#red-black-tree%EC%9D%98-%EC%82%AD%EC%A0%9Cremove)
  - [Red-Black Tree의 복잡도(Complexity)](https://github.com/TaeHyungK/computer-science/blob/master/DataStructure/Red-Black%20Tree.md#red-black-tree%EC%9D%98-%EB%B3%B5%EC%9E%A1%EB%8F%84complexity)
- [B+ Tree](https://github.com/TaeHyungK/computer-science/blob/master/DataStructure/B%2B%20Tree.md#b-tree)
  - [B+ Tree 란?](https://github.com/TaeHyungK/computer-science/blob/master/DataStructure/B%2B%20Tree.md#b-tree-%EB%9E%80)







---

###### 참고

- [WeareSoft : tech-interview](https://github.com/WeareSoft/tech-interview/blob/master/contents/datastructure.md)

- [나를 개발하자, PYH : [자료구조] 그래프(Graph)](https://kosaf04pyh.tistory.com/131)
- [Manducku`s Code : 자료구조 Graph - 그래프의 정의와 표현 By java](https://manducku.tistory.com/21)
- [zerocho : 그래프(graph)](https://www.zerocho.com/category/Algorithm/post/584b9033580277001862f16c)
- [heejeong Kwon : [자료구조] 그래프(Graph)란](https://gmlwjd9405.github.io/2018/08/13/data-structure-graph.html)
- [heejeong Kwon : [알고리즘] 너비 우선 탐색(BFS)이란](https://gmlwjd9405.github.io/2018/08/15/algorithm-bfs.html)
- [heejeong Kwon : [알고리즘] 깊이 우선 탐색(DFS)이란](https://gmlwjd9405.github.io/2018/08/14/algorithm-dfs.html)
- [위키피디아 : Tree](https://ko.wikipedia.org/wiki/%ED%8A%B8%EB%A6%AC_%EA%B5%AC%EC%A1%B0)
- [진짜 개발자 : 자료구조 - 트리(Tree)란](https://galid1.tistory.com/174)
- [코딩팩토리 : [Alogrithm] 트리(Tree)구조란 무엇인가?](https://coding-factory.tistory.com/231)
- [heejeong Kwon : [자료구조] 트리(Tree)란](https://gmlwjd9405.github.io/2018/08/12/data-structure-tree.html)
- [덕's IT Story : 레드블랙 트리(Red-black tree)](https://itstory.tk/entry/%EB%A0%88%EB%93%9C%EB%B8%94%EB%9E%99-%ED%8A%B8%EB%A6%ACRed-black-tree)
- [Nesoy Blog : RedBlack Tree에 대해](https://nesoy.github.io/articles/2018-08/Algorithm-RedblackTree)
- [Tech Interview : B Tree & B+ Tree](https://gyoogle.dev/blog/computer-science/data-structure/B%20Tree%20&%20B+%20Tree.html)
- [JI-DUM : B-Tree](http://www.jidum.com/jidums/view.do?jidumId=156)
- [JI-DUM : B+Tree](http://www.jidum.com/jidums/view.do?jidumId=156)
- [인호의 IT 잡동사니 : B tree, B+ tree](https://helloino.tistory.com/113)