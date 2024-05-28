---
published: true
title: 99클럽 코테 스터디 Count Pairs Whose Sum is Less than Target
date: 2024-05-27
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

## [오늘의 문제 : Count Pairs Whose Sum is Less than Target](https://leetcode.com/problems/count-pairs-whose-sum-is-less-than-target/description/)

Given a 0-indexed integer array nums of length n and an integer target, return the number of pairs (i, j) where 0 <= i < j < n and nums[i] + nums[j] < target.

## 학습 키워드

- 리스트 탐색
- 투 포인터 알고리즘
- 효율적인 쌍 찾기

## 공부한 내용 본인의 언어로 정리하기

이번 문제에서는 리스트에서 두 요소의 합이 특정 값보다 작은 쌍을 찾는 방법을 공부했다. 이를 위해 파이썬의 리스트 탐색 기법과 투 포인터 알고리즘을 활용했다. 특히, 효율적인 탐색을 위해 리스트를 정렬하고 투 포인터를 사용하는 방법을 배웠다.

## 오늘의 회고

### 어떤 문제가 있었고, 나는 어떤 시도를 했는지

주어진 문제는 리스트에서 두 요소의 합이 특정 값보다 작은 쌍의 개수를 찾는 것이었다. 처음에는 중첩 반복문을 사용하여 모든 쌍을 확인하는 방법을 시도했으나, 이는 비효율적이었다. 이후, 투 포인터 알고리즘을 사용하여 더 효율적으로 문제를 해결할 방법을 시도했다.

### 어떻게 해결했는지

가장 간단하고 효율적인 방법은 리스트를 정렬한 후 투 포인터 알고리즘을 사용하는 것이었다. 이를 통해 문제를 해결할 수 있었다.

```python
def countPairs(nums, target):
    nums.sort()
    count = 0
    left = 0
    right = len(nums) - 1

    while left < right:
        if nums[left] + nums[right] < target:
            count += (right - left)
            left += 1
        else:
            right -= 1

    return count
```

이 코드는 리스트를 오름차순으로 정렬한 후, 두 포인터를 사용하여 리스트의 시작과 끝에서부터 탐색을 시작한다. 두 요소의 합이 타겟보다 작으면, 가능한 모든 쌍을 세고 왼쪽 포인터를 증가시키며, 그렇지 않으면 오른쪽 포인터를 감소시켜 탐색을 계속한다.

### 무엇을 새롭게 알았는지

이번 문제를 해결하면서 투 포인터 알고리즘의 유용성을 배웠다. 이를 통해 리스트의 특정 조건을 만족하는 쌍을 효율적으로 찾을 수 있었으며, 중첩 반복문을 사용하지 않고도 시간 복잡도를 줄일 수 있었다. 또한, 파이썬에서 리스트를 다루는 다양한 기법과 최적화 방법도 익혔다.

## 내일의 학습 계획

투 포인터 알고리즘에 대해서 더 자세하게 알아보기!
