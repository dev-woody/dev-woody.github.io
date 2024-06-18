---
published: true
title: 99클럽 코테 스터디 28일차 Find Words Containing Character
date: 2024-06-16
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

## [오늘의 문제 : Find Words Containing Character](https://leetcode.com/problems/shuffle-the-array/description/)

You are given a 0-indexed array of strings words and a character x.

Return an array of indices representing the words that contain the character x.

Note that the returned array may be in any order.

#### Example 1:

Input: words = ["leet","code"], x = "e"<br/>
Output: [0,1]<br/>
Explanation: "e" occurs in both words: "leet", and "code". <br/>Hence, we return indices 0 and 1.

#### Example 2:

Input: words = ["abc","bcd","aaaa","cbc"], x = "a"<br/>
Output: [0,2]<br/>
Explanation: "a" occurs in "abc", and "aaaa". Hence, we return indices 0 and 2.

#### Example 3:

Input: words = ["abc","bcd","aaaa","cbc"], x = "z"<br/>
Output: []<br/>
Explanation: "z" does not occur in any of the words. Hence, we return an empty array.

## 학습 키워드

- 리스트 순회
- 문자열 검색
- 인덱스 추적
- 파이썬 enumerate

## 오늘의 회고

### 공부한 내용 본인의 언어로 정리하기

이번 문제에서는 주어진 리스트에서 특정 문자를 포함한 단어들의 인덱스를 찾는 방법을 공부했다. 각 단어를 순회하면서 특정 문자가 포함된 단어의 인덱스를 추적하여 결과 리스트에 저장하는 방법을 배웠다.

### 어떤 문제가 있었고, 나는 어떤 시도를 했는지

주어진 문제는 단어 리스트 words와 문자 x가 주어졌을 때, x를 포함한 단어들의 인덱스를 찾는 것이었다. 이를 위해 리스트를 순회하면서 각 단어에 x가 포함되어 있는지 확인하고, 포함된 경우 그 인덱스를 결과 리스트에 저장하는 시도를 했다.

### 어떻게 해결했는지

주어진 문제를 해결하기 위해 다음과 같은 방법을 사용했다:

```python
def find_indices(words, x):
    indices = []

    for i, word in enumerate(words):
        if x in word:
            indices.append(i)

    return indices
```

이 코드는 다음과 같은 방식으로 작동한다:

- indices 리스트를 초기화하여 문자가 포함된 단어들의 인덱스를 저장한다.
- enumerate를 사용하여 리스트 words를 순회하면서 각 단어와 그 인덱스를 얻는다.
- 현재 단어에 문자 x가 포함되어 있는지 확인하고, 포함된 경우 indices 리스트에 인덱스를 추가한다.
- 최종적으로 indices 리스트를 반환하여 문자가 포함된 단어들의 인덱스를 출력한다.

### 무엇을 새롭게 알았는지

이번 문제를 해결하면서 리스트를 순회하며 특정 문자를 검색하는 방법을 배웠다. 특히, enumerate 함수를 사용하여 리스트의 인덱스와 값을 동시에 얻는 방법과, 문자열 연산을 통해 조건을 확인하는 방법을 익혔다. 이를 통해 문자열 검색과 리스트 조작 능력을 향상시킬 수 있었다.

## 내일의 학습 계획

이번 문제와 유사한 리스트 및 문자열 검색 문제를 더 풀어보는 것을 계획하고 있다. 예를 들어, 특정 조건을 만족하는 문자열을 찾거나, 문자열 변환을 통해 조건을 만족시키는 문제를 해결해 볼 예정이다. 이를 통해 리스트와 문자열 처리 능력을 더욱 향상시키고자 한다.
