---
published: true
title: 99클럽 코테 스터디 24일차 Find Center of Star Graph
date: 2024-06-12
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

## [오늘의 문제 : Find Center of Star Graph](https://leetcode.com/problems/find-center-of-star-graph/description/)

There is an undirected star graph consisting of `n` nodes labeled from `1` to `n`. A star graph is a graph where there is one center node and exactly `n - 1` edges that connect the center node with every other node.

You are given a 2D integer array `edges` where each `edges[i] = [uᵢ, vᵢ]` indicates that there is an edge between the nodes `uᵢ` and `vᵢ`. Return the center of the given star graph.

#### Example 1:

<image alt="algorithem" src="https://assets.leetcode.com/uploads/2021/02/24/star_graph.png"/>

Input: edges = [[1,2],[2,3],[4,2]]<br/>
Output: 2
Explanation: As shown in the figure above, node 2 is connected to every other node, so 2 is the center.<br/>

#### Example 2:

Input: edges = [[1,2],[5,1],[1,3],[1,4]]<br/>
Output: 1

#### Constraints:

- `3 <= n <= 10⁵`
- `edges.length == n - 1`
- `edges[i].length == 2`
- `1 <= uᵢ, vᵢ <= n`
- `uᵢ != vᵢ`
- `The given edges represent a valid star graph.`

## 학습 키워드

- 그래프 이론
- 스타 그래프
- 딕셔너리 사용
- 예외 처리

## 오늘의 회고

### 공부한 내용 본인의 언어로 정리하기

이번 문제에서는 스타 그래프에서 중앙 노드를 찾는 방법을 공부했다. 스타 그래프는 중앙 노드와 다른 모든 노드가 직접 연결된 형태의 그래프이다. 주어진 간선 리스트를 사용하여 스타 그래프의 중앙 노드를 찾는 방법을 배웠다.

### 어떤 문제가 있었고, 나는 어떤 시도를 했는지

주어진 문제는 스타 그래프의 간선 리스트 `edges`가 주어졌을 때, 중앙 노드를 찾는 것이었다. 이를 위해 각 노드의 연결 수를 세어 가장 많은 연결을 가진 노드를 중앙 노드로 판별하는 시도를 했다.

### 어떻게 해결했는지

딕셔너리를 사용하여 각 노드의 연결 수를 세고, 가장 많은 연결을 가진 노드를 반환하였다. 이를 통해 문제를 해결할 수 있었다.

```python
from typing import List

class Solution:
    def findCenter(self, edges: List[List[int]]) -> int:
        count = {}

        for i in edges:
            try:
                count[i[0]] += 1
            except:
                count[i[0]] = 1

            try:
                count[i[1]] += 1
            except:
                count[i[1]] = 1

        return max(count, key=count.get)
```

이 코드는 다음과 같은 방식으로 작동한다.

- `count` 딕셔너리를 초기화하여 각 노드의 연결 수를 저장한다.
- 간선 리스트 `edges`를 순회하면서 각 노드의 연결 수를 증가시킨다.
- `i[0]`과 `i[1]` 노드의 연결 수를 각각 증가시키기 위해 `try` 블록을 사용하여 딕셔너리에 노드가 없을 경우 예외를 처리하고 값을 초기화한다.
- 최종적으로 `max(count, key=count.get)`을 사용하여 연결 수가 가장 많은 노드를 반환한다.

### 무엇을 새롭게 알았는지

이번 문제를 해결하면서 스타 그래프의 특성과 중앙 노드를 찾는 방법을 배웠다. 특히, 딕셔너리를 사용하여 각 노드의 연결 수를 세고, 예외 처리를 통해 딕셔너리에 값을 추가하는 방법을 익혔다. 이를 통해 파이썬에서 딕셔너리를 활용한 문제 해결 능력을 향상시킬 수 있었다.

## 내일의 학습 계획

이번 문제와 유사한 그래프 이론 문제를 더 풀어보는 것을 계획하고 있다. 예를 들어, 다른 유형의 그래프 탐색 문제나, 그래프에서 특정 조건을 만족하는 노드를 찾는 문제를 해결해 볼 예정이다. 이를 통해 그래프 이론과 관련된 알고리즘 문제 해결 능력을 더욱 향상시키고자 한다.
