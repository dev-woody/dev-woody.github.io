---
published: true
title: 99클럽 코테 스터디 17일차 Split a String in Balanced Strings
date: 2024-06-05
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

## [오늘의 문제 : Split a String in Balanced Strings](https://leetcode.com/problems/split-a-string-in-balanced-strings/description/)

Balanced strings are those that have an equal quantity of 'L' and 'R' characters.

Given a balanced string s, split it into some number of substrings such that:

Each substring is balanced.
Return the maximum number of balanced strings you can obtain.

#### Example 1:

Input: s = "RLRRLLRLRL"<br/>
Output: 4<br/>
Explanation: s can be split into "RL", "RRLL", "RL", "RL", <br/>each substring contains same number of 'L' and 'R'.<br/>

#### Example 2:

Input: s = "RLRRRLLRLL"<br/>
Output: 2<br/>
Explanation: s can be split into "RL", "RRRLLRLL", each substring contains same number of 'L' and 'R'.
Note that s cannot be split into "RL", "RR", "RL", "LR", "LL", because the 2nd and 5th substrings are not balanced.

#### Example 3:

Input: s = "LLLLRRRR"<br/>
Output: 1<br/>
Explanation: s can be split into "LLLLRRRR".

#### Constraints:

- 2 <= s.length <= 1000
- s[i] is either 'L' or 'R'.
- s is a balanced string.

## 학습 키워드

- 균형 문자열
- 서브스트링
- 문자열 분할

## 오늘의 회고

### 공부한 내용 본인의 언어로 정리하기

이번 문제에서는 'L'과 'R' 문자의 개수가 동일한 균형 문자열을 주어진 균형 문자열 s에서 최대한 많이 분할하는 방법을 공부했다. 각 서브스트링도 균형 문자열이 되어야 한다는 조건을 만족하면서, 최대한 많은 균형 문자열을 찾는 방법을 배웠다.

### 어떤 문제가 있었고, 나는 어떤 시도를 했는지

주어진 문제는 균형 문자열 s를 최대한 많은 균형 문자열로 분할하는 것이었다. 이를 위해 문자열을 순회하면서 'L'과 'R'의 개수를 세어 균형이 맞을 때마다 서브스트링을 분할하는 시도를 했다. 처음에는 'R'과 'L'의 갯수 변수를 따로둬서 각자 증가시키고 같으면 초기화하는 방식으로 진행했으나 시간복잡도가 높아서 좋은 코드가 아니였다.

### 어떻게 해결했는지

가장 간단하고 효율적인 방법은 문자열을 순회하면서 'L'과 'R'의 개수를 세고, 두 개수가 같아질 때마다 균형 문자열로 분할하는 것이다. 이를 통해 문제를 해결할 수 있었다.

```python
class Solution:
    def balancedStringSplit(self, s: str) -> int:
        outPut = 0
        balance = 0

        for i in s:
            if i == 'L':
                balance += 1
            else:
                balance -= 1

            if balance == 0:
                outPut += 1

        return outPut
```

이 코드는 다음과 같은 방식으로 작동한다.

- 문자열 `s`를 순회하면서 각 문자 `i`를 확인한다.
- 문자가 'L'이면 balance를 1 증가시키고, 'R'이면 balance를 1 감소시킨다.
- balance가 0이 될 때마다 균형 문자열이 되므로, outPut을 1 증가시킨다.
  최종적으로 outPut을 반환한다.

### 무엇을 새롭게 알았는지

이번 문제를 해결하면서 문자열을 순회하며 균형을 맞추는 방법을 배웠다. 특히, balance 변수를 활용하여 'L'과 'R'의 개수를 실시간으로 추적하는 방법을 익혔다. 이를 통해 균형 문자열 문제를 효율적으로 해결할 수 있게 되었다.

## 내일의 학습 계획

이번 문제를 해결한 방법을 다른 유사한 문제에도 적용해보는 것을 계획하고 있다. 예를 들어, 다른 문자 조합으로 이루어진 균형 문자열 문제나, 다양한 조건이 추가된 문자열 분할 문제를 해결해 볼 예정이다. 이를 통해 문자열 처리 능력을 더욱 향상시키고자 한다.
