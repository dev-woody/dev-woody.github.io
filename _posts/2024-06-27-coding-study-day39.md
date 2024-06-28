---
published: true
title: 99클럽 코테 스터디 39일차 The K Weakest Rows in a Matrix

date: 2024-06-27
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

## [오늘의 문제 : The K Weakest Rows in a Matrix](https://leetcode.com/problems/the-k-weakest-rows-in-a-matrix/description/)

## 학습 키워드

- 2차원 리스트
- 리스트 내포
- 정렬

## 오늘의 회고

### 공부한 내용 본인의 언어로 정리하기

이번 문제에서는 2차원 리스트에서 각 행의 병사 수를 세고, 가장 약한 k개의 행의 인덱스를 찾는 방법을 공부했다. 각 행의 병사 수를 계산하고, 이를 기반으로 행을 정렬하여 약한 행의 인덱스를 반환하는 방법을 배웠다.

### 어떤 문제가 있었고, 나는 어떤 시도를 했는지

주어진 문제는 2차원 리스트 mat가 주어졌을 때, 각 행의 병사 수를 세고, 가장 약한 k개의 행의 인덱스를 찾는 것이었다. 이를 위해 리스트 내포를 사용하여 병사 수와 인덱스를 튜플로 저장하고, 이를 정렬하여 약한 행의 인덱스를 추출하는 시도를 했다.

### 어떻게 해결했는지

주어진 문제를 해결하기 위해 다음과 같은 방법을 사용했다.

```python
from typing import List

class Solution:
    def kWeakestRows(self, mat: List[List[int]], k: int) -> List[int]:
        soldiers_count = [(sum(row), i) for i, row in enumerate(mat)]

        soldiers_count.sort(key=lambda x: (x[0], x[1]))

        weakest_rows = [index for _, index in soldiers_count[:k]]

        return weakest_rows
```

이 코드는 다음과 같은 방식으로 작동한다.

- soldiers_count 리스트를 초기화하여 각 행의 병사 수와 인덱스를 튜플로 저장한다.
- enumerate를 사용하여 각 행의 인덱스와 행 자체를 얻고, sum(row)를 사용하여 병사 수를 계산한다.
- 병사 수와 인덱스를 튜플 (sum(row), i)로 만들어 soldiers_count 리스트에 저장한다.
- soldiers_count 리스트를 병사 수와 인덱스를 기준으로 정렬한다.
- 정렬된 리스트에서 가장 약한 k개의 행의 인덱스를 추출하여 weakest_rows 리스트에 저장한다.
- 최종적으로 weakest_rows를 반환하여 가장 약한 k개의 행의 인덱스를 출력한다.

### 무엇을 새롭게 알았는지

이번 문제를 해결하면서 2차원 리스트에서 각 행의 병사 수를 계산하고, 이를 기반으로 정렬하는 방법을 배웠다. 특히, 리스트 내포와 enumerate를 사용하여 각 행의 병사 수와 인덱스를 동시에 저장하고, 람다 함수를 사용하여 정렬 기준을 설정하는 방법을 익혔다. 이를 통해 리스트 조작과 정렬 알고리즘을 활용한 문제 해결 능력을 향상시킬 수 있었다.

## 내일의 학습 계획

이번 문제와 유사한 2차원 리스트 및 정렬 문제를 더 풀어보는 것을 계획하고 있다. 예를 들어, 특정 조건을 만족하는 행을 찾거나, 여러 기준을 조합하여 리스트를 정렬하는 문제를 해결해 볼 예정이다. 이를 통해 2차원 리스트 처리와 정렬 능력을 더욱 향상시키고자 한다.
