---
category: Data Structure
# multiple tag entries are possible
tags: [Data Structure, tree]
# thumbnail image for post
img: ":ds-logo.png"
# disable comments on this page
comments_disable: false

# publish date
# date: 2023-02-13 00:26:08 +0900
---

<p align="center"><img src="/assets/img/posts/tree.png"></p>

<p align="center">그림1</p>



> 트리 탐색 데이터 구조는 동적 셋 기능을 제공
(SEARCH, MINIMUM, MAXIMUM, PREDECESSOR, SUCCESSOR,INSERT, DELETE)

#### Binary search tree란?
+ binary tree에서 구성되었다.
+ 각 트리는 연결된 자료구조로 key, satellite data(key와 관련된 다른 값들), 각 노드 객체는 left child, right child, p(각자의 자식, 부모 노드에 대한 노드 포인터)로 구성된다.
> 만약 자식이나 부모를 놓쳤다면, 그 적절한 구성 요소로 Null pointer를 포함시킨다.

##### root node
트리 그 자체로 root(root node pointer 또는 null pointer) 요소를 가지고 있다.
root node는 부모가 null pointer인 유일한 node이다.

**시간 복잡도**
기초적인 동작은 트리의 높이에 비례하여 시간이 걸린다.
+ n개의 노드를 가진 완전한 Binary tree는 최악의 경우 $\Theta(\log n)$ 이다.
+ 만약 트리가 n개의노드들의 선형적으로 연결되었다면, $\Theta(n)$

##### 성질
```
binary search tree에 한 노드를 x라고 한다.
x의 left subtree에 y라는 노드가 있다면 y.key <= x.key이다.
right subtree에 y라는 노드가, y.key >= x.key이다.
```

##### 트리 순회(Tree Traversal)
+ 중위순회(Inorder Traversal)
+ 전위순회(Preorder Traversal)
+ 후위순회(Postorder Traversal)

[그림1](#binary-search-tree)과 같은 트리가 있다면 트리 순회에 따라 다르게 값을 출력 할 수 있다.

###### 중위순회(Inorder Traversal)
**순서**: left node -> key -> right node

**pseudocode**
```
INORDER-TREE-WALK(x)
1   if x ≠ NIL
2       INORDER-TREE-WALK(x.left)
3       print x. key
4       INORDER-TREE-WALK(x.right)
```
**중위순회를 할 경우**  
8 4 9 2 10 5 11 1 12 6 13 3 14 7 15

###### 전위순회(Preorder Traversal)
**순서**: key -> left node ->  right node
**pseudocode**
```
PREORDER-TREE-WALK(x)
1   if x ≠ NIL
2       print x. key
3       PREORDER-TREE-WALK(x.left)
4       PREORDER-TREE-WALK(x.right)
```
**전위순회를 할 경우**   
1 2 4 8 9 5 10 11 3 6 12 13 7 14 15

**pseudocode**
###### 후위순회(Postorder Traversal)
**순서**: left node -> right node -> key
```
POSTORDER-TREE-WALK(x)
1   if x ≠ NIL
2       POSTORDER-TREE-WALK(x.left)
3       POSTORDER-TREE-WALK(x.right)
4       print x. key
```
**후위순회를 할 경우**    
8 9 4 10 11 5 2 12 13 6 14 15 7 3 1


