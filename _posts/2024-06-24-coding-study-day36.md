---
published: true
title: 99클럽 코테 스터디 36일차 Final Prices With a Special Discount in a Shop

date: 2024-06-24
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

## [오늘의 문제 : Final Prices With a Special Discount in a Shop](https://leetcode.com/problems/final-prices-with-a-special-discount-in-a-shop/description/)

## 학습 키워드

- 중첩 반복문
- 할인 계산
- 리스트 조작

### 공부한 내용 본인의 언어로 정리하기

이번 문제에서는 주어진 가격 리스트에서 각 가격에 대해 가능한 최대 할인을 적용한 최종 가격을 계산하는 방법을 공부했다. 각 가격에 대해 그 이후에 나오는 가격 중 현재 가격보다 작거나 같은 값을 찾아 할인을 적용하는 방법을 배웠다.

### 어떤 문제가 있었고, 나는 어떤 시도를 했는지

주어진 문제는 가격 리스트 prices가 주어졌을 때, 각 가격에 대해 이후에 나오는 가격 중 현재 가격보다 작거나 같은 값을 찾아 할인한 후 최종 가격을 리스트로 반환하는 것이었다. 이를 위해 중첩 반복문을 사용하여 각 가격에 대해 할인을 적용하는 시도를 했다.

### 어떻게 해결했는지

주어진 문제를 해결하기 위해 다음과 같은 방법을 사용했다.

```python
from typing import List

class Solution:
    def finalPrices(self, prices: List[int]) -> List[int]:
        answer = []
        n = len(prices)

        for i in range(n):
            discount = 0
            for j in range(i + 1, n):
                if prices[j] <= prices[i]:
                    discount = prices[j]
                    break
            answer.append(prices[i] - discount)

        return answer
```

이 코드는 다음과 같은 방식으로 작동한다.

- answer 리스트를 초기화하여 최종 가격을 저장한다.
- prices 리스트의 길이 n을 저장한다.
- 첫 번째 반복문에서 각 가격에 대해 할인 금액을 초기화한다.
- 두 번째 반복문에서 현재 가격보다 작거나 같은 첫 번째 가격을 찾아 할인 금액으로 설정한다.
- 현재 가격에서 할인 금액을 뺀 값을 answer 리스트에 추가한다.
- 최종적으로 answer 리스트를 반환하여 각 가격에 대해 할인을 적용한 최종 가격을 출력한다.

### 무엇을 새롭게 알았는지

이번 문제를 해결하면서 중첩 반복문을 사용하여 리스트의 특정 조건을 만족하는 값을 찾는 방법을 배웠다. 특히, 현재 값과 이후 값을 비교하여 조건에 맞는 값을 찾고, 이를 이용해 최종 결과를 계산하는 과정을 익혔다. 이를 통해 반복문과 조건문을 활용한 문제 해결 능력을 향상시킬 수 있었다.

## 내일의 학습 계획

이번 문제와 유사한 리스트 및 조건문 문제를 더 풀어보는 것을 계획하고 있다. 예를 들어, 복잡한 조건을 만족하는 값을 찾거나, 리스트의 값을 변형하여 특정 조건을 충족시키는 문제를 해결해 볼 예정이다. 이를 통해 리스트 처리와 조건문 사용 능력을 더욱 향상시키고자 한다.
