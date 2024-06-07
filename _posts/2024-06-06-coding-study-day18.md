---
published: true
title: 99클럽 코테 스터디 18일차 Counting Bits
date: 2024-06-06
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

## [오늘의 문제 : Counting Bits](https://leetcode.com/problems/counting-bits/description/)

Given an integer n, return an array ans of length n + 1 such that for each i (0 <= i <= n), ans[i] is the number of 1's in the binary representation of i.

#### Example 1:

Input: n = 2<br/>
Output: [0,1,1]<br/>
Explanation:<br/>
0 --> 0<br/>
1 --> 1<br/>
2 --> 10<br/>

#### Example 2:

Input: n = 5<br/>
Output: [0,1,1,2,1,2]<br/>
Explanation:<br/>
0 --> 0<br/>
1 --> 1<br/>
2 --> 10<br/>
3 --> 11<br/>
4 --> 100<br/>
5 --> 101<br/>

#### Constraints:

0 <= n <= 10\*\*5

## 학습 키워드

- 이진수 변환
- 비트 카운트
- 동적 배열

## 오늘의 회고

### 공부한 내용 본인의 언어로 정리하기

이번 문제에서는 0부터 n까지의 모든 정수에 대해 각 숫자의 이진수 표현에서 1의 개수를 세는 방법을 공부했다. 파이썬의 내장 함수를 이용하여 이진수로 변환하고, 1의 개수를 카운트하여 결과를 리스트로 반환하는 방법을 배웠다.

### 어떤 문제가 있었고, 나는 어떤 시도를 했는지

주어진 문제는 0부터 n까지의 숫자 각각에 대해 이진수로 변환했을 때, 1의 개수를 세는 것이었다. 이를 위해 각 숫자를 이진수로 변환하고, 변환된 문자열에서 1의 개수를 세는 시도를 했다.

### 어떻게 해결했는지

가장 간단하고 효율적인 방법은 파이썬의 내장 함수 bin()을 이용하여 숫자를 이진수로 변환한 후, 문자열 메소드 count('1')을 사용하여 1의 개수를 세는 것이다. 이를 통해 문제를 해결할 수 있었다:

```python
from typing import List

class Solution:
    def countBits(self, n: int) -> List[int]:
        ans = [0] * (n + 1)

        for i in range(n + 1):
            ans[i] = bin(i).count('1')

        return ans
```

이 코드는 다음과 같은 방식으로 작동한다.

- `ans` 리스트를 초기화하여 0부터 n까지 각 숫자에 대한 1의 개수를 저장할 수 있도록 한다.
- 0부터 n까지 각 숫자 i에 대해, bin(i)를 이용하여 숫자를 이진수 문자열로 변환한다.
- 이진수 문자열에서 count('1')을 사용하여 1의 개수를 세고, 이를 ans 리스트의 해당 위치에 저장한다.
- 최종적으로 ans 리스트를 반환하여 0부터 n까지의 각 숫자에 대한 1의 개수를 출력한다.

### 무엇을 새롭게 알았는지

이번 문제를 해결하면서 파이썬의 내장 함수 `bin()`과 문자열 메소드 `count('1')`의 유용성을 배웠다. 특히, 숫자를 이진수로 변환하고, 이진수에서 특정 비트의 개수를 세는 방법을 익혔다. 이를 통해 파이썬에서 이진수 처리와 비트 카운팅 문제를 효율적으로 해결하는 방법을 배울 수 있었다.

## 내일의 학습 계획

이번 문제와 유사한 비트 조작 문제를 더 풀어보는 것을 계획하고 있다. 예를 들어, 비트 연산을 활용한 다른 알고리즘 문제나, 특정 조건을 만족하는 비트 패턴을 찾는 문제를 해결해 볼 예정이다. 이를 통해 비트 조작 능력을 더욱 향상시키고자 한다.
