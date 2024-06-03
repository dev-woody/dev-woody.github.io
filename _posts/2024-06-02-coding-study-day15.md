---
published: true
title: 99클럽 코테 스터디 15일차 Maximum Depth of Binary Tree
date: 2024-06-03
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

## [오늘의 문제 : Maximum Depth of Binary Tree](https://leetcode.com/problems/maximum-depth-of-binary-tree/description/)

Given the `root` of a binary tree, return its maximum depth.

A binary tree's maximum depth is the number of nodes along the longest path from the root node down to the farthest leaf node.

#### Example 1:

<image alt="binary node" src="https://assets.leetcode.com/uploads/2020/11/26/tmp-tree.jpg">

Input: root = [3,9,20,null,null,15,7]<br>
Output: 3

#### Example 2:

Input: root = [1,null,2]<br>
Output: 2

## 학습 키워드

- 이진 트리
- 재귀 함수
- 트리 탐색
- 최대 깊이

## 오늘의 회고

### 공부한 내용 본인의 언어로 정리하기

이번 문제에서는 이진 트리의 최대 깊이를 구하는 방법을 공부했다. 특히, 재귀를 이용하여 트리의 각 노드를 순회하면서 왼쪽과 오른쪽 서브트리의 깊이를 계산하고, 그 중 더 큰 값에 1을 더해 최대 깊이를 구하는 방법을 배웠다.

### 어떤 문제가 있었고, 나는 어떤 시도를 했는지

주어진 문제는 이진 트리의 최대 깊이를 구하는 것이었다. 이를 위해 재귀를 사용하여 각 노드를 탐색하고, 각 노드의 왼쪽과 오른쪽 서브트리의 깊이를 계산하는 시도를 했다.

### 어떻게 해결했는지

가장 간단하고 효율적인 방법은 재귀적으로 트리를 탐색하면서 각 노드의 왼쪽과 오른쪽 서브트리의 깊이를 계산하고, 그 중 더 큰 깊이에 1을 더하는 것이었다. 이를 통해 문제를 해결할 수 있었다:

```python
# TreeNode 클래스 정의
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right

class Solution:
    def maxDepth(self, root: Optional[TreeNode]) -> int:
        if root is None:
            return 0

        left_depth = self.maxDepth(root.left)
        right_depth = self.maxDepth(root.right)

        return max(left_depth, right_depth) + 1
```

이 코드는 다음과 같은 방식으로 작동한다.

1. maxDepth 함수는 트리를 재귀적으로 탐색하여 각 노드의 깊이를 계산한다.
2. 현재 노드가 None이면, 즉 트리가 비어있으면 0을 반환한다.
3. 왼쪽 서브트리와 오른쪽 서브트리의 깊이를 각각 재귀적으로 계산한다.
4. 왼쪽과 오른쪽 서브트리의 깊이 중 더 큰 값에 1을 더해 현재 노드의 깊이를 계산한다.
5. 최종적으로 root 노드의 깊이를 반환한다.

### 무엇을 새롭게 알았는지

이번 문제를 해결하면서 이진 트리 구조에서 재귀를 활용한 최대 깊이 계산의 중요성을 배웠다. 특히, 재귀를 통해 각 노드를 탐색하면서 깊이를 계산하는 방법과 트리 구조를 유지하면서 작업을 수행하는 기법을 익혔다. 이를 통해 파이썬에서 재귀를 활용한 최대 깊이 문제를 효율적으로 해결할 수 있게 되었다.

## 내일의 학습 계획

생각보다 시간 복잡도가 높게 나와서 다른 방법으로 풀이를 하려고 해봤다. chat GPT의 도움을 받아서 작성한 코드다.

```python
class Solution:
    def maxDepth(self, root: Optional[TreeNode]) -> int:
        if root is None:
            return 0

        stack = [(root, 1)]
        max_depth = 0

        while stack:
            node, depth = stack.pop()
            if node:
                max_depth = max(max_depth, depth)
                stack.append((node.left, depth + 1))
                stack.append((node.right, depth + 1))

        return max_depth
```

스택을 사용하여 노드와 현재 깊이를 저장한다. <br>
스택이 빌 때까지 노드를 팝하여 현재 깊이를 갱신하고, 왼쪽과 오른쪽 자식을 스택에 추가한다. <br>
스택에서 노드를 팝할 때마다 최대 깊이를 갱신한다.

이 방식은 속도가 훨씬 빨랐다. 같은 문제라도 여러가시 방법을 생각해서 풀어봐야겠다.
