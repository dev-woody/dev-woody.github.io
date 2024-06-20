---
published: true
title: 99클럽 코테 스터디 32일차 Neither Minimum nor Maximum

date: 2024-06-20
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

## [오늘의 문제 : Neither Minimum nor Maximum](https://leetcode.com/problems/neither-minimum-nor-maximum/description/)

Given an integer array nums containing distinct positive integers, find and return any number from the array that is neither the minimum nor the maximum value in the array, or -1 if there is no such number.

Return the selected integer.

#### Example 1:

Input: nums = [3,2,1,4]<br/>
Output: 2<br/>
Explanation: In this example, the minimum value is 1 and the maximum value is 4. Therefore, either 2 or 3 can be valid answers.

#### Example 2:

Input: nums = [1,2]<br/>
Output: -1<br/>
Explanation: Since there is no number in nums that is neither the maximum nor the minimum, we cannot select a number that satisfies the given condition. Therefore, there is no answer.

#### Example 3:

Input: nums = [2,1,3]<br/>
Output: 2<br/>
Explanation: Since 2 is neither the maximum nor the minimum value in nums, it is the only valid answer.

#### Constraints:

- 1 <= nums.length <= 100
- 1 <= nums[i] <= 100
- All values in nums are distinct

## 학습 키워드

- 리스트 순회
- 최소값과 최대값 찾기
- 조건문

## 오늘의 회고

### 공부한 내용 본인의 언어로 정리하기

이번 문제에서는 리스트에서 최소값과 최대값이 아닌 다른 숫자를 찾는 방법을 공부했다. 리스트를 순회하면서 최소값과 최대값을 찾고, 그 값들을 제외한 나머지 값 중 하나를 반환하는 방법을 배웠다.

### 어떤 문제가 있었고, 나는 어떤 시도를 했는지

주어진 문제는 숫자 리스트 nums가 주어졌을 때, 최소값과 최대값이 아닌 다른 값을 찾는 것이었다. 이를 위해 리스트를 두 번 순회하여 첫 번째 순회에서 최소값과 최대값을 찾고, 두 번째 순회에서 그 값들을 제외한 나머지 값을 반환하는 시도를 했다.

### 어떻게 해결했는지

주어진 문제를 해결하기 위해 다음과 같은 방법을 사용했다.

```python
from typing import List

class Solution:
    def findNonMinOrMax(self, nums: List[int]) -> int:
        if len(nums) < 3:
            return -1

        min_val = float('inf')
        max_val = float('-inf')

        for num in nums:
            if num < min_val:
                min_val = num
            if num > max_val:
                max_val = num

        for num in nums:
            if num != min_val and num != max_val:
                return num

        return -1
```

이 코드는 다음과 같은 방식으로 작동한다.

- 리스트의 길이가 3보다 작으면 -1을 반환한다.
- min_val과 max_val을 각각 무한대와 음의 무한대로 초기화한다.
- 리스트 nums를 순회하면서 최소값과 최대값을 찾는다.
- 다시 리스트를 순회하면서 최소값과 최대값이 아닌 첫 번째 값을 반환한다.
  만약 최소값과 최대값이 아닌 값이 없으면 -1을 반환한다.

### 무엇을 새롭게 알았는지

이번 문제를 해결하면서 리스트에서 최소값과 최대값을 찾는 방법과 조건문을 활용하여 특정 조건을 만족하는 값을 반환하는 방법을 배웠다. 특히, 무한대를 이용해 초기 값을 설정하고, 리스트를 두 번 순회하여 문제를 해결하는 과정을 익혔다. 이를 통해 리스트 조작과 조건문 활용 능력을 향상시킬 수 있었다.

## 내일의 학습 계획

이번 문제와 유사한 리스트 및 조건문 문제를 더 풀어보는 것을 계획하고 있다. 예를 들어, 특정 조건을 만족하는 값을 찾거나, 리스트의 값들을 조작하여 문제를 해결하는 문제를 해결해 볼 예정이다. 이를 통해 리스트 처리와 조건문 사용 능력을 더욱 향상시키고자 한다.
