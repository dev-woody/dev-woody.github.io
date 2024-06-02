---
published: true
title: 99클럽 코테 스터디 13일차 Evaluate Boolean Binary Tree
date: 2024-06-01
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

## [오늘의 문제 : Evaluate Boolean Binary Tree](https://leetcode.com/problems/evaluate-boolean-binary-tree/)

## 학습 키워드

- 이진 트리
- 재귀 함수
- 논리 연산

## 공부한 내용 본인의 언어로 정리하기

이번 문제에서는 이진 트리의 구조와 탐색 방법을 공부했다. 특히, 재귀를 이용하여 트리의 각 노드를 순회하고, 리프 노드에서 시작하여 논리 연산을 통해 트리 전체를 평가하는 방법을 배웠다.

## 오늘의 회고

### 어떤 문제가 있었고, 나는 어떤 시도를 했는지

주어진 문제는 이진 트리의 각 노드를 논리 연산자로 평가하는 것이었다. 이를 위해 재귀를 사용하여 각 노드를 평가하고, 내부 노드에서 OR 또는 AND 연산을 수행하여 트리 전체를 평가하는 방법을 시도했다.

### 어떻게 해결했는지

가장 간단하고 효율적인 방법은 리프 노드의 값을 평가하고, 내부 노드에서 OR 또는 AND 연산을 수행하여 트리 전체를 평가하는 것이었다. 이를 통해 문제를 해결할 수 있었다.

```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right

class Solution:
    def evaluateTree(self, root: TreeNode) -> bool:
        # 리프 노드이면 그 값을 반환
        if not root.left and not root.right:
            return root.val == 1

        # 왼쪽과 오른쪽 자식을 재귀적으로 평가
        left_val = self.evaluateTree(root.left)
        right_val = self.evaluateTree(root.right)

        # 현재 노드의 값에 따라 OR 또는 AND 연산 수행
        if root.val == 2:  # OR 연산자
            return left_val or right_val
        elif root.val == 3:  # AND 연산자
            return left_val and right_val
```

이 코드는 다음과 같은 방식으로 동작한다.

1. evaluateTree 함수는 트리를 재귀적으로 탐색하며 각 노드를 평가한다.
2. 리프 노드에 도달하면 그 값을 반환한다. 여기서 값이 1이면 True, 그렇지 않으면 False를 반환한다.
3. 내부 노드에서는 왼쪽과 오른쪽 자식을 재귀적으로 평가한 후, 노드의 값에 따라 OR 또는 AND 연산을 수행한다.
4. 노드의 값이 2이면 OR 연산을 수행하고, 값이 3이면 AND 연산을 수행한다.

### 무엇을 새롭게 알았는지

이번 문제를 해결하면서 이진 트리 구조에서 재귀를 활용한 노드 평가의 중요성을 배웠다. 특히, 논리 연산자를 이용하여 트리 전체를 평가하는 방법과 재귀의 강력함을 다시 한번 깨달았다. 이를 통해 파이썬에서 재귀와 논리 연산을 결합한 문제 해결 방법을 익히게 되었다.

## 내일의 학습 계획

이진트리 노드에 대해서 더 자세하게 알아봐야겠다. 좀 이해했다 생각했는데 아직 잘 모르는 것 같다.
