---
published: true
title: 99클럽 코테 스터디 23일차 Count Negative Numbers in a Sorted Matrix
date: 2024-06-11
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

## [오늘의 문제 : Count Negative Numbers in a Sorted Matrix](https://leetcode.com/problems/count-negative-numbers-in-a-sorted-matrix/description/)

Given a `m x n` matrix `grid` which is sorted in non-increasing order both row-wise and column-wise, return the number of negative numbers in `grid`.

#### Example 1:

Input: grid = [[4,3,2,-1],[3,2,1,-1],[1,1,-1,-2],[-1,-1,-2,-3]]<br/>
Output: 8<br/>
Explanation: There are 8 negatives number in the matrix.<br/>

#### Example 2:

Input: grid = [[3,2],[1,0]]<br/>
Output: 0

#### Constraints:

- `m == grid.length`
- `n == grid[i].length`
- `1 <= m, n <= 100`
- `-100 <= grid[i][j] <= 100`

## 학습 키워드

- 2차원 배열
- 중첩 반복문
- 음수 카운트

## 오늘의 회고

### 공부한 내용 본인의 언어로 정리하기

이번 문제에서는 2차원 배열에서 음수 값을 세는 방법을 공부했다. 주어진 2차원 배열에서 각 요소를 확인하여 음수인 경우 그 개수를 세는 방법을 배웠다.

### 어떤 문제가 있었고, 나는 어떤 시도를 했는지

주어진 문제는 2차원 배열 `grid`에서 음수 값을 모두 찾아 그 개수를 반환하는 것이었다. 이를 위해 중첩 반복문을 사용하여 배열의 각 요소를 확인하고, 음수 값을 세는 시도를 했다.

### 어떻게 해결했는지

가장 간단하고 효율적인 방법은 중첩 반복문을 사용하여 배열의 각 요소를 순회하면서 음수 값을 찾는 것이다. 이를 통해 문제를 해결할 수 있었다.

```python
from typing import List

class Solution:
    def countNegatives(self, grid: List[List[int]]) -> int:
        num = 0
        for i in grid:
            for l in i:
                if l < 0:
                    num += 1

        return num
```

이 코드는 다음과 같은 방식으로 작동한다.

- `num` 변수를 0으로 초기화하여 음수 값을 세는 카운터로 사용한다.
- 2차원 배열 `grid`를 순회하면서 각 행 `i`를 확인한다.
- 각 행 `i`에서 요소 `l`을 확인하여 `l`이 음수이면 `num`을 1 증가시킨다.
- 최종적으로 `num`을 반환하여 배열에서 발견된 음수 값의 개수를 출력한다.

### 무엇을 새롭게 알았는지

이번 문제를 해결하면서 2차원 배열을 순회하며 특정 조건을 만족하는 요소를 세는 방법을 배웠다. 특히, 중첩 반복문을 사용하여 배열을 효율적으로 탐색하고 조건에 맞는 값을 카운트하는 방법을 익혔다. 이를 통해 반복문과 조건문을 활용한 문제 해결 능력을 향상시킬 수 있었다.

## 내일의 학습 계획

이번 문제와 유사한 2차원 배열 탐색 문제를 더 풀어보는 것을 계획하고 있다. 예를 들어, 다른 조건을 만족하는 요소를 찾는 문제나, 배열을 변형하여 특정 조건을 충족시키는 문제를 해결해 볼 예정이다. 이를 통해 배열 탐색 및 조작 능력을 더욱 향상시키고자 한다.
