---
published: true
title: 99클럽 코테 스터디 25일차 Shuffle the Array
date: 2024-06-14
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

## [오늘의 문제 : Shuffle the Array](https://leetcode.com/problems/shuffle-the-array/description/)

Given the array `nums` consisting of `2n` elements in the form `[x1,x2,...,xn,y1,y2,...,yn]`.

Return the array in the form `[x1,y1,x2,y2,...,xn,yn]`.

#### Example 1:

Input: nums = [2,5,1,3,4,7], n = 3<br/>
Output: [2,3,5,4,1,7]<br/>
Explanation: Since x1=2, x2=5, x3=1, y1=3, y2=4, y3=7 then the answer is [2,3,5,4,1,7].

#### Example 2:

Input: nums = [1,2,3,4,4,3,2,1], n = 4<br/>
Output: [1,4,2,3,3,2,4,1]

#### Example 3:

Input: nums = [1,1,2,2], n = 2<br/>
Output: [1,2,1,2]

#### Constraints:

- `1 <= n <= 500`
- `nums.length == 2n`
- `1 <= nums[i] <= 10^3`

## 학습 키워드

- 리스트 분할
- 리스트 병합
- 반복문
- 순열

## 오늘의 회고

### 공부한 내용 본인의 언어로 정리하기

이번 문제에서는 주어진 리스트를 두 부분으로 나누고, 두 리스트의 요소를 번갈아가며 병합하는 방법을 공부했다. 이를 통해 하나의 새로운 리스트를 생성하여 원하는 순서로 요소를 배치하는 방법을 배웠다.

### 어떤 문제가 있었고, 나는 어떤 시도를 했는지

주어진 문제는 리스트 `nums`와 정수 `n`이 주어졌을 때, 리스트를 두 부분으로 나누고 이들을 번갈아가며 병합하여 새로운 리스트를 만드는 것이었다. 이를 위해 리스트를 두 부분으로 나누고, 반복문을 사용하여 병합하는 시도를 했다.

### 어떻게 해결했는지

리스트를 두 부분으로 나눈 후, 반복문을 통해 번갈아가며 요소를 병합하였다. 이를 통해 문제를 해결할 수 있었다.

```python
from typing import List

class Solution:
    def shuffle(self, nums: List[int], n: int) -> List[int]:
        numX = nums[:n]
        numY = nums[n:]
        answer = []

        for i in range(len(numX)):
            answer.append(numX[i])
            answer.append(numY[i])

        return answer
```

이 코드는 다음과 같은 방식으로 작동한다.

- 리스트 `nums`를 두 부분 `numX`와 `numY`로 나눈다. `numX`는 처음부터 n까지의 요소를, `numY`는 `n`부터 끝까지의 요소를 가진다.
- `answer` 리스트를 초기화하여 결과를 저장한다.
- `numX`의 길이만큼 반복문을 실행하여, numX와 numY의 요소를 번갈아가며 `answer` 리스트에 추가한다.
- 최종적으로 `answer를` 반환하여 두 리스트의 요소가 번갈아가며 배치된 새로운 리스트를 출력한다.

### 무엇을 새롭게 알았는지

이번 문제를 해결하면서 리스트를 분할하고, 분할된 리스트를 병합하는 방법을 배웠다. 특히, 슬라이싱을 사용하여 리스트를 쉽게 분할하는 방법과 반복문을 통해 두 리스트의 요소를 번갈아가며 병합하는 방법을 익혔다. 이를 통해 리스트 조작과 반복문을 활용한 문제 해결 능력을 향상시킬 수 있었다.

## 내일의 학습 계획

좀 더 간단한 코드를 작성을 했는데 시간 복잡도가 증가했다. 이유를 파악하고 이번 문제와 유사한 리스트 조작 문제를 더 풀어보는 것을 계획하고 있다. 예를 들어, 다른 조건의 리스트 병합 문제나, 리스트를 특정 패턴에 따라 변형하는 문제를 해결해 볼 예정이다. 이를 통해 리스트 처리 능력을 더욱 향상시키고자 한다.
