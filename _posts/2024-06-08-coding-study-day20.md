---
published: true
title: 99클럽 코테 스터디 20일차 Fibonacci Number
date: 2024-06-08
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

## [오늘의 문제 : Fibonacci Number](https://leetcode.com/problems/fibonacci-number/description/)

## 학습 키워드

- 피보나치 수열
- 반복문
- 동적 프로그래밍

## 오늘의 회고

### 공부한 내용 본인의 언어로 정리하기

이번 문제에서는 피보나치 수열의 n번째 숫자를 구하는 방법을 공부했다. 피보나치 수열은 첫 두 숫자가 0과 1로 시작하고, 그 다음 숫자는 앞 두 숫자의 합으로 구성된다. 이를 바탕으로 주어진 n에 대해 피보나치 수열의 n번째 숫자를 구하는 방법을 배웠다.

### 어떤 문제가 있었고, 나는 어떤 시도를 했는지

주어진 문제는 피보나치 수열의 n번째 숫자를 구하는 것이었다. 이를 위해 반복문을 사용하여 이전 두 숫자를 더해 현재 숫자를 구하는 시도를 했다.

### 어떻게 해결했는지

가장 효율적인 방법은 반복문을 통해 이전 두 숫자를 더해 현재 숫자를 구하는 것이다. 이를 통해 문제를 해결할 수 있었다:

```python
class Solution:
    def fib(self, n: int) -> int:
        if n == 0:
            return 0
        elif n == 1:
            return 1

        prev2, prev1 = 0, 1

        for i in range(2, n + 1):
            current = prev1 + prev2
            prev2 = prev1
            prev1 = current

        return prev1
```

이 코드는 다음과 같은 방식으로 작동한다.

- n이 0이면 0을 반환한다.
- n이 1이면 1을 반환한다.
- prev2와 prev1을 초기화하여 각각 0과 1로 설정한다.
- 2부터 n까지의 숫자에 대해 반복문을 실행하여 현재 숫자를 prev1과 prev2의 합으로 계산한다.
- prev2를 prev1으로, prev1을 현재 숫자로 업데이트한다.
- 최종적으로 prev1을 반환하여 피보나치 수열의 n번째 숫자를 출력한다.

### 무엇을 새롭게 알았는지

이번 문제를 해결하면서 피보나치 수열의 구성 원리와 이를 반복문을 사용하여 효율적으로 구현하는 방법을 배웠다. 특히, 동적 프로그래밍 기법을 활용하여 이전 값을 저장하고 이를 이용해 다음 값을 계산하는 방법을 익혔다. 이를 통해 파이썬에서 반복문과 동적 프로그래밍을 활용한 문제 해결 능력을 향상시킬 수 있었다.

## 내일의 학습 계획

이번 문제와 유사한 수열을 다루는 문제를 더 풀어보는 것을 계획하고 있다. 예를 들어, 다른 유형의 수열 문제나, 재귀와 반복문을 혼합하여 사용하는 문제를 해결해 볼 예정이다. 이를 통해 알고리즘 문제 해결 능력을 더욱 향상시키고자 한다.
