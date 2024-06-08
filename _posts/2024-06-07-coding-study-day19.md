---
published: true
title: 99클럽 코테 스터디 19일차 Pascal's Triangle
date: 2024-06-07
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

## [오늘의 문제 : Pascal's Triangle](https://leetcode.com/problems/pascals-triangle/description/)

Given an integer numRows, return the first numRows of Pascal's triangle.

In Pascal's triangle, each number is the sum of the two numbers directly above it as shown:

<image alt="Pascal's Triangle" src="https://upload.wikimedia.org/wikipedia/commons/0/0d/PascalTriangleAnimated2.gif">

#### Example 1:

Input: numRows = 5<br/>
Output: [[1],[1,1],[1,2,1],[1,3,3,1],[1,4,6,4,1]]<br/>

#### Example 2:

Input: numRows = 1<br/>
Output: [[1]]<br/>

#### Constraints:

- 1 <= numRows <= 30

## 학습 키워드

- 파스칼의 삼각형
- 이차원 리스트
- 반복문

## 오늘의 회고

### 공부한 내용 본인의 언어로 정리하기

이번 문제에서는 파스칼의 삼각형을 생성하는 방법을 공부했다. 파스칼의 삼각형은 각 행의 첫 번째와 마지막 요소가 1이며, 각 행의 중간 요소는 바로 위 행의 두 요소를 더한 값으로 구성된다. 이를 바탕으로 주어진 행의 수(numRows)에 따라 파스칼의 삼각형을 생성하는 방법을 배웠다.

### 어떤 문제가 있었고, 나는 어떤 시도를 했는지

주어진 문제는 numRows 행을 가지는 파스칼의 삼각형을 생성하는 것이었다. 이를 위해 각 행의 값을 계산하고, 이차원 리스트에 저장하여 삼각형을 구성하는 시도를 했다.

### 어떻게 해결했는지

가장 효율적인 방법은 첫 번째 행을 초기화하고, 각 행을 반복문을 통해 생성하면서 이전 행의 값을 이용해 현재 행의 값을 계산하는 것이다. 이를 통해 문제를 해결할 수 있었다.

```python
from typing import List

class Solution:
    def generate(self, numRows: int) -> List[List[int]]:
        if numRows == 0:
            return []

        triangle = [[1]]  # Start with the first row

        for row_num in range(1, numRows):
            row = [1]  # Every row starts with 1
            prev_row = triangle[row_num - 1]

            # Generate the middle elements of the row
            for j in range(1, row_num):
                row.append(prev_row[j - 1] + prev_row[j])

            row.append(1)  # Every row ends with 1
            triangle.append(row)

        return triangle
```

이 코드는 다음과 같은 방식으로 작동한다.

- numRows가 0이면 빈 리스트를 반환한다.
- triangle 리스트를 초기화하여 첫 번째 행을 [1]로 시작한다.
- 각 행 번호(row_num)에 대해, 현재 행을 생성하고 첫 번째 요소로 1을 추가한다.
- 이전 행(prev_row)의 값을 이용하여 현재 행의 중간 요소들을 계산하고 추가한다.
- 현재 행의 마지막 요소로 1을 추가하고, triangle 리스트에 현재 행을 추가한다.
- 최종적으로 triangle 리스트를 반환하여 파스칼의 삼각형을 출력한다.

### 무엇을 새롭게 알았는지

이번 문제를 해결하면서 파스칼의 삼각형의 구성 원리와 이를 프로그래밍으로 구현하는 방법을 배웠다. 특히, 이차원 리스트를 활용하여 각 행을 생성하고, 이전 행의 값을 이용하여 새로운 값을 계산하는 방법을 익혔다. 이를 통해 파이썬에서 반복문과 리스트 조작을 활용한 문제 해결 능력을 향상시킬 수 있었다.

## 내일의 학습 계획

이번 문제와 유사한 이차원 리스트를 다루는 문제를 더 풀어보는 것을 계획하고 있다. 예를 들어, 행렬 조작 문제나, 특정 조건을 만족하는 이차원 배열 생성 문제를 해결해 볼 예정이다. 이를 통해 이차원 데이터 처리 능력을 더욱 향상시키고자 한다.
