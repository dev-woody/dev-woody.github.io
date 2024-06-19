---
published: true
title: 99클럽 코테 스터디 31일차 Decode the Message

date: 2024-06-19
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

## [오늘의 문제 : Decode the Message](https://leetcode.com/problems/decode-the-message/description/)

You are given the strings key and message, which represent a cipher key and a secret message, respectively. The steps to decode message are as follows:

1. Use the first appearance of all 26 lowercase English letters in key as the order of the substitution table.
2. Align the substitution table with the regular English alphabet.
3. Each letter in message is then substituted using the table.
4. Spaces ' ' are transformed to themselves.
5. For example, given key = "happy boy" (actual key would have at least one instance of each letter in the alphabet), we have the partial substitution table of ('h' -> 'a', 'a' -> 'b', 'p' -> 'c', 'y' -> 'd', 'b' -> 'e', 'o' -> 'f').

Return the decoded message.

#### Example 1:

<image alt="coding test" src="https://assets.leetcode.com/uploads/2022/05/08/ex1new4.jpg"/>

Input: key = "the quick brown fox jumps over the lazy dog", message = "vkbs bs t suepuv"<br/>
Output: "this is a secret"<br/>
Explanation: The diagram above shows the substitution table.
It is obtained by taking the first appearance of each letter in "the quick brown fox jumps over the lazy dog".

#### Example 2:

<image alt="coding test" src="https://assets.leetcode.com/uploads/2022/05/08/ex2new.jpg"/>

Input: key = "eljuxhpwnyrdgtqkviszcfmabo", message = "zwx hnfx lqantp mnoeius ycgk vcnjrdb"<br/>
Output: "the five boxing wizards jump quickly"<br/>
Explanation: The diagram above shows the substitution table.
It is obtained by taking the first appearance of each letter in "eljuxhpwnyrdgtqkviszcfmabo".

#### Constraints:

- 26 <= key.length <= 2000
- key consists of lowercase English letters and ' '.
- key contains every letter in the English alphabet ('a' to 'z') at least once.
- 1 <= message.length <= 2000
- message consists of lowercase English letters and ' '.

## 학습 키워드

- 문자열 조작
- 치환 암호
- 딕셔너리

## 오늘의 회고

### 공부한 내용 본인의 언어로 정리하기

이번 문제에서는 주어진 키(key)를 이용하여 치환 암호를 풀어내는 방법을 공부했다. 주어진 키를 사용하여 치환 테이블을 생성하고, 이를 이용해 메시지를 복호화하는 과정을 배웠다.

### 어떤 문제가 있었고, 나는 어떤 시도를 했는지

주어진 문제는 문자열 key와 message가 주어졌을 때, key를 기반으로 치환 테이블을 만들어 message를 복호화하는 것이었다. 이를 위해 문자열의 각 문자를 순회하여 치환 테이블을 생성하고, 메시지의 각 문자를 치환하는 시도를 했다.

### 어떻게 해결했는지

주어진 문제를 해결하기 위해 다음과 같은 방법을 사용했다.

```python
class Solution:
    def decodeMessage(self, key: str, message: str) -> str:
        seen = set()
        sub_table = []
        for char in key:
            if char not in seen and char.isalpha():
                seen.add(char)
                sub_table.append(char)
        for char in "abcdefghijklmnopqrstuvwxyz":
            if char not in seen:
                sub_table.append(char)

        sub_dict = {sub_table[i]: chr(97 + i) for i in range(26)}

        decoded_message = []
        for char in message:
            if char.isalpha():
                decoded_message.append(sub_dict[char])
            else:
                decoded_message.append(char)

        return ''.join(decoded_message)
```

이 코드는 다음과 같은 방식으로 작동한다.

- seen 집합을 초기화하여 키에 등장한 문자를 추적한다.
- sub_table 리스트를 초기화하여 치환 테이블을 생성한다.
- 키 key를 순회하면서 알파벳 문자를 sub_table에 추가하고 seen 집합에 기록한다.
- a-z까지의 알파벳을 순회하면서 seen에 없는 문자를 sub_table에 추가한다.
- sub_table을 기반으로 sub_dict 딕셔너리를 생성하여 각 문자를 치환할 문자를 매핑한다.
- 메시지 message를 순회하면서 알파벳 문자는 치환하고, 그렇지 않은 문자는 그대로 decoded_message 리스트에 추가한다.
- 최종적으로 decoded_message를 문자열로 결합하여 복호화된 메시지를 반환한다.

### 무엇을 새롭게 알았는지

이번 문제를 해결하면서 문자열을 치환하는 방법과 딕셔너리를 사용해 문자를 매핑하는 방법을 배웠다. 특히, 주어진 키를 이용해 치환 테이블을 만들고 이를 사용해 메시지를 복호화하는 과정을 익혔다. 이를 통해 문자열 조작과 딕셔너리 활용 능력을 향상시킬 수 있었다.

## 내일의 학습 계획

이번 문제와 유사한 문자열 치환 및 복호화 문제를 더 풀어보는 것을 계획하고 있다. 예를 들어, 다른 유형의 치환 암호 문제나, 문자열 변환을 통해 특정 조건을 만족시키는 문제를 해결해 볼 예정이다. 이를 통해 문자열 처리와 치환 알고리즘 능력을 더욱 향상시키고자 한다.
