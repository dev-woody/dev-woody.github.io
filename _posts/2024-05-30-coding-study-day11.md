---
published: true
title: 99클럽 코테 스터디 11일차 Range Sum of BST
date: 2024-05-30
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

## [오늘의 문제 : Range Sum of BST](https://leetcode.com/problems/range-sum-of-bst/description/?source=submission-ac)

Given the root node of a binary search tree and two integers low and high, return the sum of values of all nodes with a value in the inclusive range [low, high].

Example 1:

<img alt="bst" src="https://assets.leetcode.com/uploads/2020/11/05/bst1.jpg">

Input: root = [10,5,15,3,7,null,18], low = 7, high = 15<br>
Output: 32
Explanation: Nodes 7, 10, and 15 are in the range [7, 15]. 7 + 10 + 15 = 32.

Example 2:

<img alt="bst" src="https://assets.leetcode.com/uploads/2020/11/05/bst2.jpg">

Input: root = [10,5,15,3,7,13,18,1,null,6], low = 6, high = 10 <br>
Output: 23
Explanation: Nodes 6, 7, and 10 are in the range [6, 10]. 6 + 7 + 10 = 23.

## 학습 키워드

- 이진 검색 트리 (BST)
- 깊이 우선 탐색 (DFS)
- 범위 합 계산

## 공부한 내용 본인의 언어로 정리하기

이번 문제에서는 이진 검색 트리의 구조와 특성을 이용하여, 특정 범위 내의 노드 값을 합산하는 방법을 공부했다. 이를 위해 파이썬의 DFS 기법을 활용하여 트리의 각 노드를 순회하면서 조건에 맞는 값을 합산하는 방법을 배웠다.

## 오늘의 회고

### 어떤 문제가 있었고, 나는 어떤 시도를 했는지

주어진 문제는 이진 검색 트리에서 특정 범위 내의 노드 값을 합산하는 것이었다. 처음에는 root가 리스트라고 생각하여 반복문을 통해 조건에 맞는지 판단하고 배열에 저장하고 합을 구하는 방식을 쓰려고 했는데 TreeNode는 그렇게 할 수 없다는 에러를 받았다. 구글에 찾아보고 DFS를 사용하여 트리를 탐색하고, 각 노드의 값이 주어진 범위 내에 있을 경우 합산하는 방법을 시도했다.

### 어떻게 해결했는지

가장 간단하고 효율적인 방법은 이진 검색 트리의 특성을 활용하여, 주어진 범위를 벗어나는 탐색을 줄이고, 조건에 맞는 노드 값을 합산하는 것이었다. 이를 통해 문제를 해결할 수 있었다:

```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right

class Solution:
    def rangeSumBST(self, root: Optional[TreeNode], low: int, high: int) -> int:

        def dfs(node):
            if not node:
                return 0

            total = 0
            if low <= node.val <= high:
                total += node.val

            if node.val > low:
                total += dfs(node.left)

            if node.val < high:
                total += dfs(node.right)

            return total

        return dfs(root)
```

이 코드는 다음과 같은 방식으로 동작한다.

1. dfs 함수는 트리를 깊이 우선 탐색(DFS)한다.
2. 각 노드에 대해, 노드 값이 주어진 범위 (low와 high 사이)에 있으면 그 값을 합산한다.
3. 노드 값이 low보다 크면 왼쪽 자식을 탐색하고, high보다 작으면 오른쪽 자식을 탐색한다.
4. 최종적으로 모든 조건을 만족하는 노드 값의 합을 반환한다.

### 무엇을 새롭게 알았는지

이번 문제를 해결하면서 이진 검색 트리의 효율적인 탐색 방법을 배웠다. 특히, DFS를 활용하여 조건부로 값을 합산하는 방법과 트리 구조를 활용한 문제 해결 기법을 익혔다. 이를 통해 트리 데이터를 다루는 다양한 기법을 배우게 되었다.

## 내일의 학습 계획

트리구조에 대해서 명확하게 이해하고 깊이 우선 탐색(DFS) 과 너비 우선 탐색(BFS)에 대해서 확실하게 공부하자.
