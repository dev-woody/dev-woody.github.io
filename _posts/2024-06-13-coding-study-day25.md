---
published: true
title: 99클럽 코테 스터디 25일차 Minimum Number of Moves to Seat Everyone
date: 2024-06-13
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

## [오늘의 문제 : Minimum Number of Moves to Seat Everyone](https://leetcode.com/problems/minimum-number-of-moves-to-seat-everyone/description/?envType=daily-question&envId=2024-06-13)

There are `n` seats and `n` students in a room. You are given an array `seats` of length `n`, where `seats[i]` is the position of the `i`<sup>`th`</sup> seat. You are also given the array `students` of length `n`, where `students[j]` is the position of the `j`<sup>`th`</sup> student.

You may perform the following move any number of times:

- Increase or decrease the position of the ith student by 1 (i.e., moving the ith student from position x to x + 1 or x - 1)

Return the minimum number of moves required to move each student to a seat such that no two students are in the same seat.

Note that there may be multiple seats or students in the same position at the beginning.

#### Example 1:

Input: seats = [3,1,5], students = [2,7,4]<br/>
Output: 4<br/>
Explanation: The students are moved as follows:

- The first student is moved from from position 2 to position 1 using 1 move.
- The second student is moved from from position 7 to position 5 using 2 moves.
- The third student is moved from from position 4 to position 3 using 1 move.
  In total, 1 + 2 + 1 = 4 moves were used.

#### Example 2:

Input: seats = [4,1,5,9], students = [1,3,2,6]<br/>
Output: 7<br/>
Explanation: The students are moved as follows:

- The first student is not moved.
- The second student is moved from from position 3 to position 4 using 1 move.
- The third student is moved from from position 2 to position 5 using 3 moves.
- The fourth student is moved from from position 6 to position 9 using 3 moves.
  In total, 0 + 1 + 3 + 3 = 7 moves were used.

#### Example 3:

Input: seats = [2,2,6,6], students = [1,3,2,6]<br/>
Output: 4<br/>
Explanation: Note that there are two seats at position 2 and two seats at position 6.
The students are moved as follows:

- The first student is moved from from position 1 to position 2 using 1 move.
- The second student is moved from from position 3 to position 6 using 3 moves.
- The third student is not moved.
- The fourth student is not moved.
  In total, 1 + 3 + 0 + 0 = 4 moves were used.

#### Constraints:

- `n == seats.length == students.length`
- `1 <= n <= 100`
- `1 <= seats[i], students[j] <= 100`

## 학습 키워드

- 정렬
- 차이 계산
- 절대값
- 최소 이동 횟수

## 오늘의 회고

### 공부한 내용 본인의 언어로 정리하기

이번 문제에서는 주어진 좌석 배열과 학생 배열을 정렬하여 학생들이 좌석에 앉을 때 최소 이동 횟수를 계산하는 방법을 공부했다. 각 학생이 해당 좌석에 앉기 위해 필요한 이동 횟수를 구하고, 그 이동 횟수를 모두 더하여 최소 이동 횟수를 계산하는 방법을 배웠다.

### 어떤 문제가 있었고, 나는 어떤 시도를 했는지

주어진 문제는 두 배열 seats와 students가 주어졌을 때, 학생들이 좌석에 앉기 위해 필요한 최소 이동 횟수를 구하는 것이었다. 이를 위해 배열을 정렬하고, 각 요소의 차이를 절대값으로 구해 이동 횟수를 계산하는 시도를 했다.

### 어떻게 해결했는지

두 배열을 정렬한 후, 각 요소의 차이를 절대값으로 구해 이동 횟수를 더했다. 이를 통해 문제를 해결할 수 있었다.

```python
from typing import List

class Solution:
    def minMovesToSeat(self, seats: List[int], students: List[int]) -> int:
        seats.sort()
        students.sort()

        answer = 0

        for i in range(len(seats)):
            move = abs(seats[i] - students[i])
            answer += move

        return answer
```

이 코드는 다음과 같은 방식으로 작동한다.

- `seats`와 `students` 배열을 각각 정렬한다.
- `answer` 변수를 0으로 초기화하여 총 이동 횟수를 저장한다.
- 정렬된 배열을 순회하면서 각 좌석과 학생의 차이를 절대값으로 계산하고, 그 값을 `answer`에 더한다.
- 최종적으로 `answer`를 반환하여 학생들이 좌석에 앉기 위해 필요한 최소 이동 횟수를 출력한다.

### 무엇을 새롭게 알았는지

이번 문제를 해결하면서 배열을 정렬하고, 정렬된 배열의 요소 간의 차이를 이용해 문제를 해결하는 방법을 배웠다. 특히, `abs()` 함수를 사용하여 음수 값을 양수로 변환하는 방법과 이를 통해 이동 횟수를 정확히 계산하는 방법을 익혔다. 이를 통해 정렬과 반복문을 활용한 문제 해결 능력을 향상시킬 수 있었다.

## 내일의 학습 계획

이번 문제와 유사한 배열 정렬 및 차이 계산 문제를 더 풀어보는 것을 계획하고 있다. 예를 들어, 다른 조건의 배열 정렬 문제나, 배열 간의 거리 계산 문제를 해결해 볼 예정이다. 이를 통해 배열 처리 능력을 더욱 향상시키고자 한다.
