---
published: true
title: 99클럽 코테 스터디 14일차 Invert Binary Tree
date: 2024-06-02
categories: [Coding Test]
tags:
  [
    99클럽,
    코딩테스트 준비,
    개발자 취업,
    항해99,
    TIL,
    개발스터디,
    개발,
    알고리즘,
    파이썬,
    Python
  ]
toc: true
toc_sticky: true
toc_label: "항해99"
---

<img alt='sail99' src="https://github.com/dev-woody/dev-woody.github.io/assets/87690037/9acd8a60-ff3e-48fb-a317-38c699c8bf0e">

## [오늘의 문제 : Invert Binary Tree](https://leetcode.com/problems/invert-binary-tree/description/)

Given the `root` of a binary tree, invert the tree, and return its root.

#### Example 1:

<image alt="binary-tree" src="https://assets.leetcode.com/uploads/2021/03/14/invert1-tree.jpg"/>

Input: root = [4,2,7,1,3,6,9]<br/>
Output: [4,7,2,9,6,3,1]

#### Example 2:

<image alt="binary-tree" src="https://assets.leetcode.com/uploads/2021/03/14/invert2-tree.jpg"/>

Input: root = [2,1,3]<br/>
Output: [2,3,1]

#### Example 3:

Input: root = []<br/>
Output: []

#### Constraints:

- The number of nodes in the tree is in the range `[0, 100]`.<br/>
- `-100 <= Node.val <= 100`

## 학습 키워드

- 이진 트리
- 재귀 함수
- 트리 탐색

## 오늘의 회고

### 공부한 내용 본인의 언어로 정리하기

이번 문제에서는 이진 트리의 구조와 탐색 방법을 공부했다. 특히, 재귀를 이용하여 트리의 각 노드를 순회하면서 왼쪽 자식과 오른쪽 자식을 교환하는 방법을 배웠다.

### 어떤 문제가 있었고, 나는 어떤 시도를 했는지

주어진 문제는 이진 트리의 각 노드를 반전시키는 것이었다. 이를 위해 재귀를 사용하여 각 노드를 탐색하고, 탐색 중에 왼쪽 자식과 오른쪽 자식을 교환하는 시도를 했다.

### 어떻게 해결했는지

가장 간단하고 효율적인 방법은 재귀적으로 트리를 탐색하면서 각 노드의 자식을 교환하는 것이었다. 이를 통해 문제를 해결할 수 있었다:

```python

# TreeNode 클래스 정의
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right

class Solution:
    def invertTree(self, root: Optional[TreeNode]) -> Optional[TreeNode]:
        if root is None:
            return None

        root.left, root.right = root.right, root.left
        self.invertTree(root.left)
        self.invertTree(root.right)

        return root
```

이 코드는 다음과 같은 방식으로 작동한다.

1. `invertTree` 함수는 트리를 재귀적으로 탐색하며 각 노드를 반전시킨다.
2. 현재 노드가 None이면, 즉 트리가 비어있으면 None을 반환한다.
3. 현재 노드의 왼쪽 자식과 오른쪽 자식을 교환한다.
4. 왼쪽 자식과 오른쪽 자식을 재귀적으로 반전시킨다.
5. 최종적으로 반전된 트리의 루트를 반환한다.

### 무엇을 새롭게 알았는지

이번 문제를 해결하면서 이진 트리 구조에서 재귀를 활용한 노드 반전의 중요성을 배웠다. 특히, 재귀를 통해 각 노드를 탐색하면서 자식을 교환하는 방법과 트리의 구조를 유지하면서 작업을 수행하는 기법을 익혔다. 이를 통해 파이썬에서 재귀를 활용한 트리 반전 문제를 효율적으로 해결할 수 있게 되었다.

## 내일의 학습 계획

이진트리에 대한 이해도 높이기!
