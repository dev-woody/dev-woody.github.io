---
published: true
title: 99클럽 코테 스터디 12일차 Find a Corresponding Node of a Binary Tree in a Clone of That Tree
date: 2024-05-31
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

## [오늘의 문제 : Find a Corresponding Node of a Binary Tree in a Clone of That Tree](https://leetcode.com/problems/find-a-corresponding-node-of-a-binary-tree-in-a-clone-of-that-tree/)

## 학습 키워드

- 이진 트리
- 트리 탐색
- 재귀 함수

## 공부한 내용 본인의 언어로 정리하기

이번 문제에서는 이진 트리의 구조와 탐색 방법을 공부했다. 특히, 재귀를 이용하여 트리를 탐색하는 기법과 주어진 이진 트리의 클론에서 동일한 노드를 찾는 방법을 배웠다.

## 오늘의 회고

### 어떤 문제가 있었고, 나는 어떤 시도를 했는지

주어진 문제는 원본 이진 트리와 동일하게 클론된 트리에서 특정 타겟 노드를 찾는 것이었다. 이를 위해 재귀를 활용하여 원본 트리와 클론된 트리를 동시에 탐색하고, 타겟 노드를 찾는 방법을 시도했다.

### 어떻게 해결했는지

가장 간단하고 효율적인 방법은 원본 트리의 노드를 탐색하면서, 동시에 클론된 트리의 대응하는 노드를 찾는 방식이었다. 이를 위해 재귀를 사용하여 트리의 좌우 자식을 탐색하며 타겟 노드를 찾았다:

```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, x):
#         self.val = x
#         self.left = None
#         self.right = None

class Solution:
    def getTargetCopy(self, original: TreeNode, cloned: TreeNode, target: TreeNode) -> TreeNode:
        if original is None:
            return None
        if original is target:
            return cloned

        left_result = self.getTargetCopy(original.left, cloned.left, target)
        if left_result is not None:
            return left_result

        right_result = self.getTargetCopy(original.right, cloned.right, target)
        return right_result
```

이 코드는 다음과 같은 방식으로 동작한다.

1. getTargetCopy 함수는 원본 트리와 클론된 트리를 동시에 탐색한다.
2. 현재 노드가 target 노드와 동일한지 확인한다. 동일하다면 클론된 트리의 현재 노드를 반환한다.
3. 현재 노드가 target 노드가 아니라면, 좌우 자식을 재귀적으로 탐색한다.
4. 좌측 자식에서 타겟 노드를 찾으면 그 결과를 반환하고, 그렇지 않으면 우측 자식을 탐색하여 결과를 반환한다.

### 무엇을 새롭게 알았는지

이번 문제를 해결하면서 이진 트리 구조에서 재귀를 활용한 탐색의 중요성을 배웠다. 이를 통해 클론된 트리에서 대응되는 노드를 찾는 방법을 익혔다. 또한, 트리 탐색의 효율적인 방법과 재귀의 강력함을 다시 한번 깨달았다.

## 내일의 학습 계획

재귀함수와 깊이 우선 탐색, 넓이 우선탐색, 트리노드에 대헤서 정리하기
