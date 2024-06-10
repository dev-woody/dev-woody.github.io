---
published: true
title: 99클럽 코테 스터디 22일차 Search Insert Position
date: 2024-06-10
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

## [오늘의 문제 : Search Insert Position](https://leetcode.com/problems/search-insert-position/description/)

Given a sorted array of distinct integers and a target value, return the index if the target is found. If not, return the index where it would be if it were inserted in order.

You must write an algorithm with `O(log n)` runtime complexity.

#### Example 1:

- Input: nums = [1,3,5,6], target = 5
- Output: 2

#### Example 2:

- Input: nums = [1,3,5,6], target = 2
- Output: 1

#### Example 3:

- Input: nums = [1,3,5,6], target = 7
- Output: 4

#### Constraints:

- `1 <= nums.length <= 10**4`
- `-10**4 <= nums[i] <= 10**4`
- `nums` contains distinct values sorted in ascending order.
- `10**4 <= target <= 10**4`

## 학습 키워드

- 정렬된 배열
- 삽입 위치 찾기

## 오늘의 회고

### 공부한 내용 본인의 언어로 정리하기

이번 문제에서는 정렬된 배열에서 특정 값을 찾거나, 해당 값이 없다면 삽입할 위치를 찾는 방법을 공부했다. 주어진 정렬된 배열에서 목표 값을 찾고, 값이 없다면 그 값을 삽입할 위치의 인덱스를 반환하는 방법을 배웠다.

### 어떤 문제가 있었고, 나는 어떤 시도를 했는지

주어진 문제는 정렬된 배열 nums와 목표 값 `target`이 주어졌을 때, `target`이 존재하면 그 인덱스를, 존재하지 않으면 `target`을 삽입할 위치의 인덱스를 반환하는 것이었다. 이를 위해 배열을 순회하면서 `target`보다 작은 값의 개수를 세어 삽입할 위치를 찾는 시도를 했다.

### 어떻게 해결했는지

가장 간단하고 효율적인 방법은 배열을 순회하면서 target보다 작은 값을 찾고, 그 값을 기반으로 삽입 위치를 결정하는 것이다. 이를 통해 문제를 해결할 수 있었다.

```python
from typing import List

class Solution:
    def searchInsert(self, nums: List[int], target: int) -> int:
        index = 0
        for i in nums:
            if i < target:
                index += 1
            elif i == target:
                break
        return index
```

이 코드는 다음과 같은 방식으로 작동한다.

- `index`를 0으로 초기화한다.
- 배열 `nums`를 순회하면서 현재 값 `i`가 `target`보다 작으면 `index`를 1 증가시킨다.
- 현재 값 `i`가 `target`과 같으면 반복문을 종료한다.
- 최종적으로 `index`를 반환하여 `target`의 인덱스나 삽입 위치를 출력한다.

### 무엇을 새롭게 알았는지

이번 문제를 해결하면서 정렬된 배열에서 특정 값을 찾거나 삽입할 위치를 찾는 방법을 배웠다. 특히, 배열을 순회하며 조건에 맞는 값을 찾고, 해당 조건에 따라 삽입 위치를 결정하는 방법을 익혔다. 이를 통해 파이썬에서 반복문과 조건문을 활용한 문제 해결 능력을 향상시킬 수 있었다.

## 내일의 학습 계획

이번 문제와 유사한 배열 탐색 문제를 더 풀어보는 것을 계획하고 있다. 예를 들어, 이진 탐색을 활용한 문제나, 조건에 따라 배열을 조작하는 문제를 해결해 볼 예정이다. 이를 통해 알고리즘 문제 해결 능력을 더욱 향상시키고자 한다.
