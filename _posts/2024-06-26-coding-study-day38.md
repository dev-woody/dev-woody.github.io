---
published: true
title: 99클럽 코테 스터디 38일차 Delete Greatest Value in Each Row

date: 2024-06-26
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

## [오늘의 문제 : Delete Greatest Value in Each Row](https://leetcode.com/problems/delete-greatest-value-in-each-row/description/)

## 학습 키워드

- 리스트 조작
- 반복문
- 최대값 찾기

## 오늘의 회고

### 공부한 내용 본인의 언어로 정리하기

이번 문제에서는 2차원 리스트에서 각 행의 최대값을 반복적으로 추출하여 합산하는 방법을 공부했다. 각 행에서 최대값을 찾아 제거하고, 이 최대값들 중 가장 큰 값을 누적하여 최종 결과를 계산하는 방법을 배웠다.

### 어떤 문제가 있었고, 나는 어떤 시도를 했는지

주어진 문제는 2차원 리스트 grid에서 각 행의 최대값을 찾아 제거하고, 그 최대값들 중 가장 큰 값을 누적하여 최종 결과를 계산하는 것이었다. 이를 위해 반복문을 사용하여 각 행의 최대값을 찾고, 이를 합산하는 시도를 했다.

### 어떻게 해결했는지

주어진 문제를 해결하기 위해 다음과 같은 방법을 사용했다.

```python
def calculate_max_sum(grid: List[List[int]]) -> int:
    answer = 0
    while grid[0]:  # Continue until the grid rows are empty
        max_elements = []
        for row in grid:
            max_value = max(row)
            max_elements.append(max_value)
            row.remove(max_value)

        answer += max(max_elements)
    return answer
```

이 코드는 다음과 같은 방식으로 작동한다.

- answer 변수를 0으로 초기화하여 최대값들의 합을 저장한다.
- 첫 번째 행이 비어있을 때까지 반복문을 실행한다.
- 각 반복에서 max_elements 리스트를 초기화하여 각 행의 최대값을 저장한다.
- 각 행을 순회하면서 최대값을 찾아 max_elements에 추가하고, 그 값을 행에서 - 제거한다.
- max_elements 리스트의 최대값을 answer에 누적한다.
- 최종적으로 answer를 반환하여 최대값들의 합을 출력한다.

### 무엇을 새롭게 알았는지

이번 문제를 해결하면서 2차원 리스트에서 최대값을 추출하고 제거하는 방법을 배웠다. 특히, 반복문을 사용하여 각 행의 최대값을 찾아 리스트에서 제거하는 방법과, 이러한 값을 누적하여 최종 결과를 계산하는 과정을 익혔다. 이를 통해 리스트 조작과 반복문 활용 능력을 향상시킬 수 있었다.

## 내일의 학습 계획

이번 문제와 유사한 2차원 리스트 및 최대값 찾기 문제를 더 풀어보는 것을 계획하고 있다. 예를 들어, 복잡한 조건을 만족하는 값을 찾거나, 리스트의 값을 변형하여 특정 조건을 충족시키는 문제를 해결해 볼 예정이다. 이를 통해 리스트 처리와 조건문 사용 능력을 더욱 향상시키고자 한다.
