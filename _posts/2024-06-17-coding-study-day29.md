---
published: true
title: 99클럽 코테 스터디 29일차 Count Items Matching a Rule
date: 2024-06-17
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

## [오늘의 문제 : Count Items Matching a Rule](https://leetcode.com/problems/count-items-matching-a-rule/description/)

You are given an array `items`, where each `items[i] = [typeᵢ, colorᵢ, nameᵢ]` describes the type, color, and name of the `iᵗʰ` item. You are also given a rule represented by two strings, `ruleKey` and ruleValue.

The `iᵗʰ` item is said to match the rule if one of the following is true:

- `ruleKey == "type"` and `ruleValue == typeᵢ`.
- `ruleKey == "color"` and `ruleValue == colorᵢ`.
- `ruleKey == "name"` and `ruleValue == nameᵢ`.

Return the number of items that match the given rule.

#### Example 1:

Input: items = [["phone","blue","pixel"],["computer","silver","lenovo"],["phone","gold","iphone"]], ruleKey = "color", ruleValue = "silver"<br/>
Output: 1<br/>
Explanation: There is only one item matching the given rule, which is ["computer","silver","lenovo"].

#### Example 2:

Input: items = [["phone","blue","pixel"],["computer","silver","phone"],["phone","gold","iphone"]], ruleKey = "type", ruleValue = "phone"<br/>
Output: 2<br/>
Explanation: There are only two items matching the given rule, which are ["phone","blue","pixel"] and ["phone","gold","iphone"]. Note that the item ["computer","silver","phone"] does not match.

#### Constraints:

- `1 <= items.length <= 10⁴`
- `1 <= typeᵢ.length, colorᵢ.length, nameᵢ.length, ruleValue.length <= 10`
- `ruleKey` is equal to either `"type"`, `"color"`, or `"name"`.
- All strings consist only of lowercase letters.

## 학습 키워드

- 리스트 순회
- 조건문
- 문자열 비교

## 오늘의 회고

### 공부한 내용 본인의 언어로 정리하기

이번 문제에서는 주어진 리스트의 아이템 중 특정 규칙에 맞는 아이템의 개수를 세는 방법을 공부했다. 각 아이템을 순회하면서 주어진 규칙 키와 규칙 값을 비교하여 일치하는 아이템의 개수를 추적하는 방법을 배웠다.

### 어떤 문제가 있었고, 나는 어떤 시도를 했는지

주어진 문제는 아이템 리스트 `items`와 규칙 키 `ruleKey`, 규칙 값 `ruleValue`가 주어졌을 때, 해당 규칙에 맞는 아이템의 개수를 세는 것이었다. 이를 위해 리스트를 순회하면서 각 아이템의 특정 속성과 규칙 값을 비교하는 시도를 했다.

### 어떻게 해결했는지

주어진 문제를 해결하기 위해 다음과 같은 방법을 사용했다.

```python
from typing import List

class Solution:
    def countMatches(self, items: List[List[str]], ruleKey: str, ruleValue: str) -> int:
        answer = 0

        for i in items:
            if ruleKey == "type":
                if i[0] == ruleValue:
                    answer += 1
            elif ruleKey == "color":
                if i[1] == ruleValue:
                    answer += 1
            elif ruleKey == "name":
                if i[2] == ruleValue:
                    answer += 1

        return answer
```

이 코드는 다음과 같은 방식으로 작동한다.

- answer 변수를 0으로 초기화하여 규칙에 맞는 아이템의 개수를 저장한다.
- 아이템 리스트 items를 순회하면서 각 아이템 i를 확인한다.
- ruleKey가 "type"인 경우, 아이템의 첫 번째 요소와 ruleValue를 비교하여 일치하면 answer를 증가시킨다.
- ruleKey가 "color"인 경우, 아이템의 두 번째 요소와 ruleValue를 비교하여 일치하면 answer를 증가시킨다.
- ruleKey가 "name"인 경우, 아이템의 세 번째 요소와 ruleValue를 비교하여 일치하면 answer를 증가시킨다.
- 최종적으로 answer를 반환하여 규칙에 맞는 아이템의 개수를 출력한다.

### 무엇을 새롭게 알았는지

이번 문제를 해결하면서 리스트를 순회하고 조건문을 사용하여 특정 조건을 만족하는 요소를 세는 방법을 배웠다. 특히, 문자열 비교와 조건문을 활용하여 다양한 조건에 따라 동적으로 값을 비교하는 방법을 익혔다. 이를 통해 리스트 조작과 조건문 활용 능력을 향상시킬 수 있었다.

## 내일의 학습 계획

이번 문제와 유사한 리스트 및 조건문 문제를 더 풀어보는 것을 계획하고 있다. 예를 들어, 복잡한 조건을 만족하는 요소를 찾거나, 여러 조건을 조합하여 값을 계산하는 문제를 해결해 볼 예정이다. 이를 통해 조건문과 리스트 처리 능력을 더욱 향상시키고자 한다.
