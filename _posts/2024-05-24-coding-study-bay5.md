---
published: true
title: 99클럽 코테 스터디 5일차 TIL 숫자게임
date: 2024-05-24
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

<img alt='sail99' src="https://github.com/dev-woody/dev-woody.github.io/assets/87690037/9acd8a60-ff3e-48fb-a317-38c699c8bf0e" >

## [오늘의 문제 : leetcode 숫자게임](https://leetcode.com/problems/minimum-number-game/submissions/1269911173/)

## 학습 키워드

- 리스트 정렬
- 파이썬 리스트의 추가 및 제거
- 알고리즘 효율성

## 공부한 내용 본인의 언어로 정리하기

이번 문제에서는 리스트에서 가장 작은 두 개의 값을 반복적으로 찾아서 다른 리스트에 추가하는 방법을 공부했다. 이를 위해 파이썬의 min() 함수를 사용하여 리스트에서 최소값을 찾고, append()로 새로운 리스트에 추가한 후 remove()로 원래 리스트에서 제거하는 방법을 사용했다. 또한, pop()을 통해 리스트의 마지막 요소를 제거하고 이를 다른 리스트에 추가하는 과정도 포함되었다.

## 오늘의 회고

### 어떤 문제가 있었고, 나는 어떤 시도를 했는지

주어진 문제는 리스트에서 가장 작은 두 개의 숫자를 반복적으로 찾아서 다른 리스트에 추가하는 것이었다. 처음에는 for문을 사용했으나 작동하지 않았다. 따라서 while 루프를 사용하여 리스트의 길이를 초과하지 않도록 하는 방법을 사용했다. 또한, 중복 코드와 불필요한 코드를 제거하여 효율적인 코드를 작성하려고 시도했다.

### 어떻게 해결했는지

```python
class Solution:
    def numberGame(self, nums: List[int]) -> List[int]:
        arr = []

        while nums:
            basket = [min(nums)]
            nums.remove(basket[0])

            if nums:
                basket.append(min(nums))
                nums.remove(basket[1])

            arr.append(basket.pop())
            if basket:
                arr.append(basket.pop())

        return arr
```

이렇게 수정함으로써 코드가 더욱 간결해지고 명확해졌습니다. 이제 리스트에서 최소값을 반복적으로 찾아 제거하고, 이를 새로운 리스트에 추가하는 과정이 효율적으로 처리됩니다.

### 무엇을 새롭게 알았는지

이번 문제를 해결하면서 리스트에서 최소값을 반복적으로 찾는 방법이 비효율적일 수 있음을 알게 되었다. 또한, 리스트에서 요소를 제거할 때 발생할 수 있는 문제점과 이를 방지하는 방법도 배웠다. 마지막으로, 코드의 간결화와 효율성이 얼마나 중요한지도 깨달았다.

## 내일의 학습 계획

왜 for문으로 했을때 동작하지않았는지 알아보기
