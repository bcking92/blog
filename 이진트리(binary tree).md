## 이진트리(binary tree)

#### 개념

- 이진트리는 트리 중에서 모든 노드(node)들이 최대 2개의 서브트리(sub tree)를 갖는 형태의 트리를 말합니다. 그러므로 모든 노드들은 자식 노드(child node)를 최대 2개 까지만 가질 수 있습니다. 

  

  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/f/f7/Binary_tree.svg/220px-Binary_tree.svg.png">

  

- 자식 노드는 왼쪽 자식 노드(left child node)와 오른쪽 자식 노드(right child node)로 구분하여 말합니다.

- 이진트리의 종류는 기본적으로

  - 포화 이진 트리(Full Binary Tree) : 모든 레벨에 노드가 포화상태로 차 있는 이진 트리
  - 완전 이진 트리(Complete Binary Tree) : 중간에 빈자리 없이 1번부터 n번까지의 노드가 순서대로 채워져 있는 이진 트리
  - 편향 이진 트리(Skewed Binary Tree) : 최소 개수의 노드를 가지면서 한쪽 방향의 노드가 가진 이진 트리

  가 있고 그 밖에도  균형 이진 트리(balanced binary tree), 무한 완전 이진 트리(infinite complete binary tree) 등이 있습니다.

#### 특징

- 레벨 i 인 이진 트리의 노드의 최대 개수는 2 ^ i 개이고(포화 이진트리일 경우) 최소 개수는 i + 1개 (단말 노드(leaf node)를 제외한 모든 노드의 자식 노드가 1개일 경우)입니다.

- 완전 이진트리에서 노드의 번호를 1부터 매겼을 때, 노드 번호가 N이고 부모 노드가 존재한다면 부모 노드의 번호는 floor(N/2) = (N을 2로나눈 몫)이 됩니다. 이 성질을 이용하여 부모노드를 찾아 갈 수 있습니다.

  반대로 노드의 번호가 N이고 자식노드가 존재한다면 자식 노드의 번호는 2N + 1, 2N + 2 가 됩니다.

- 그럼 이진 트리를 코드로 만들면 어떻게 표현할 수 있을까요?

  코드로 표현하기 위한 방법은 여러가지가 있지만 1차배열을 이용하는 방법과 2차배열을 이용하는 방법을 해보겠습니다. 

  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/f/f7/Binary_tree.svg/220px-Binary_tree.svg.png">

```python
# 위와 같은 트리를 표현해보겠습니다.
# 먼저 1차원 배열을 이용하는 방법입니다.

tree = [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0]
```



#### 순회(traversal)

- 순회는 각각의 노드를 정확히 한 번만 방문하는 과정을 말합니다. 순회에는 3가지 방법이 있습니다.

  - 전위 순회(pre-order traversal)
    - 자손 노드(descendant node)보다 현재노드를 먼저 방문하는 방식입니다. 
    - [현재노드 방문 V - 왼쪽 서브트리 순회 L - 오른쪽 서브트리 순회 R] 방식으로 순회합니다.(VLR)
  - 중위 순회(in-order traversal)
    - 왼쪽 자손 노드, 현재 노드, 오른쪽 자손 노드 순으로 방문하는 방식입니다.
    - [왼쪽 서브트리 순회L - 현재 노드 방문 V - 오른쪽 서브트리 순회 R] 방식으로 순회합니다. (LVR)
  - 후위 순회(post-order traversal)
    - 현재 노드보다 자손 노드를 먼저 방문하는 방식입니다.
    - [왼쪽 서브트리 순회L - 오른쪽 서브트리 순회 R - 현재 노드 방문 V] 방식으로 순회합니다. (LRV)

  

