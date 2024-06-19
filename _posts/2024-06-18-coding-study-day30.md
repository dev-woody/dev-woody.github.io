---
published: true
title: 99클럽 코테 스터디 30일차 Shuffle String
date: 2024-06-18
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

## [오늘의 문제 : Shuffle String](https://leetcode.com/problems/shuffle-string/description/)

You are given a string `s` and an integer array `indices` of the same length. The string s will be shuffled such that the character at the `iᵗʰ` position moves to `indices[i]` in the shuffled string.

Return the shuffled string.

#### Example 1:

<image alt="algorythm" src="https://assets.leetcode.com/uploads/2020/07/09/q1.jpg" />

Input: s = "codeleet", indices = [4,5,6,7,0,2,1,3]<br/>
Output: "leetcode"<br/>
Explanation: As shown, "codeleet" becomes "leetcode" after shuffling.

#### Example 2:

Input: s = "abc", indices = [0,1,2]<br/>
Output: "abc"<br/>
Explanation: After shuffling, each character remains in its position.

## 학습 키워드

- 문자열 조작
- 리스트 순회
- 인덱스 조작

## 오늘의 회고

### 공부한 내용 본인의 언어로 정리하기

이번 문제에서는 주어진 문자열을 인덱스 배열에 따라 섞는 방법을 공부했다. 각 문자를 주어진 인덱스 위치에 배치하여 최종적으로 섞인 문자열을 생성하는 방법을 배웠다.

### 어떤 문제가 있었고, 나는 어떤 시도를 했는지

주어진 문제는 문자열 s와 인덱스 배열 indices가 주어졌을 때, indices에 지정된 위치에 맞게 문자열을 재배열하는 것이었다. 이를 위해 문자열의 각 문자를 인덱스 배열에 따라 배치하는 시도를 했다.

### 어떻게 해결했는지

주어진 문제를 해결하기 위해 다음과 같은 방법을 사용했다:

```python
from typing import List

class Solution:
    def restoreString(self, s: str, indices: List[int]) -> str:
        shuffled = [''] * len(s)

        for i, index in enumerate(indices):
            shuffled[index] = s[i]

        return ''.join(shuffled)
```

이 코드는 다음과 같은 방식으로 작동한다.

- shuffled 리스트를 초기화하여 문자열의 길이만큼 빈 문자열을 갖는 리스트를 생성한다.
- enumerate를 사용하여 indices 배열을 순회하면서 각 인덱스와 해당 인덱스에 배치될 문자열의 문자를 얻는다.
- shuffled 리스트의 index 위치에 문자열 s의 i번째 문자를 배치한다.
- 최종적으로 ''.join(shuffled)를 사용하여 리스트를 문자열로 결합하여 재배열된 문자열을 반환한다.

### 무엇을 새롭게 알았는지

이번 문제를 해결하면서 문자열을 주어진 인덱스 배열에 따라 재배열하는 방법을 배웠다. 특히, 리스트를 사용하여 문자열의 특정 위치에 문자를 배치하는 방법과 enumerate를 사용하여 인덱스와 값을 동시에 순회하는 방법을 익혔다. 이를 통해 문자열 조작과 리스트 활용 능력을 향상시킬 수 있었다.

## 내일의 학습 계획

이번 문제와 유사한 문자열 및 인덱스 조작 문제를 더 풀어보는 것을 계획하고 있다. 예를 들어, 문자열을 특정 조건에 따라 변형하거나, 인덱스 기반으로 문자열을 재배치하는 문제를 해결해 볼 예정이다. 이를 통해 문자열 처리와 인덱스 조작 능력을 더욱 향상시키고자 한다.
