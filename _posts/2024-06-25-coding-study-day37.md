---
published: true
title: 99클럽 코테 스터디 37일차 Baseball Game

date: 2024-06-25
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

## [오늘의 문제 : Baseball Game](https://leetcode.com/problems/baseball-game/description/)

## 학습 키워드

- 스택
- 조건문
- 리스트 조작

## 오늘의 회고

### 공부한 내용 본인의 언어로 정리하기

이번 문제에서는 문자열로 이루어진 연산 리스트를 처리하여 최종 점수를 계산하는 방법을 공부했다. 연산 리스트는 '+', 'D', 'C'와 정수로 구성되며, 각 연산에 따라 스택을 조작하여 점수를 계산하는 방법을 배웠다.

### 어떤 문제가 있었고, 나는 어떤 시도를 했는지

주어진 문제는 연산 리스트 operations가 주어졌을 때, 각 연산을 처리하여 최종 점수를 계산하는 것이었다. 이를 위해 스택을 사용하여 각 연산을 처리하고, 최종적으로 스택에 남은 점수를 합산하는 시도를 했다.

### 어떻게 해결했는지

주어진 문제를 해결하기 위해 다음과 같은 방법을 사용했다.

```python
from typing import List

class Solution:
    def calPoints(self, operations: List[str]) -> int:
        record = []

        for op in operations:
            if op == '+':
                record.append(record[-1] + record[-2])
            elif op == 'D':
                record.append(2 * record[-1])
            elif op == 'C':
                record.pop()
            else:  # It's an integer
                record.append(int(op))

        return sum(record)
```

이 코드는 다음과 같은 방식으로 작동한다.

- record 리스트를 초기화하여 점수를 저장한다.
- operations 리스트를 순회하면서 각 연산을 처리한다.
- '+' 연산의 경우, 스택의 마지막 두 점수를 더하여 record에 추가한다.
- 'D' 연산의 경우, 스택의 마지막 점수를 두 배로 하여 record에 추가한다.
- 'C' 연산의 경우, 스택의 마지막 점수를 제거한다.
- 숫자의 경우, 정수로 변환하여 record에 추가한다.
- 최종적으로 record 리스트의 모든 점수를 합산하여 반환한다.

### 무엇을 새롭게 알았는지

이번 문제를 해결하면서 스택을 사용하여 조건문을 통해 다양한 연산을 처리하는 방법을 배웠다. 특히, 스택을 사용하여 마지막 두 요소를 참조하거나 제거하는 방법과 조건에 따라 다른 연산을 수행하는 과정을 익혔다. 이를 통해 스택과 조건문을 활용한 문제 해결 능력을 향상시킬 수 있었다.

## 내일의 학습 계획

이번 문제와 유사한 스택 및 조건문 문제를 더 풀어보는 것을 계획하고 있다. 예를 들어, 복잡한 조건을 만족하는 값을 찾거나, 스택을 사용하여 데이터를 조작하는 문제를 해결해 볼 예정이다. 이를 통해 스택 처리와 조건문 사용 능력을 더욱 향상시키고자 한다.
