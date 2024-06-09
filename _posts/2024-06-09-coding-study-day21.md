---
published: true
title: 99클럽 코테 스터디 21일차 Divisor Game
date: 2024-06-09
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

## [오늘의 문제 : Divisor Game](https://leetcode.com/problems/divisor-game/description/)

Alice and Bob take turns playing a game, with Alice starting first.

Initially, there is a number n on the chalkboard. On each player's turn, that player makes a move consisting of:

- Choosing any x with 0 < x < n and n % x == 0.
- Replacing the number n on the chalkboard with n - x.

Also, if a player cannot make a move, they lose the game.

Return true if and only if Alice wins the game, assuming both players play optimally.

#### Example 1:

Input: n = 2<br/>
Output: true<br/>
Explanation: Alice chooses 1, and Bob has no more moves.

#### Example 2:

Input: n = 3<br/>
Output: false<br/>
Explanation: Alice chooses 1, Bob chooses 1, and Alice has no more moves.

#### Constraints:

1 <= n <= 1000

## 학습 키워드

- 나누기 게임
- 게임 이론
- 짝수와 홀수

## 오늘의 회고

### 공부한 내용 본인의 언어로 정리하기

이번 문제에서는 나누기 게임에서 Alice가 항상 승리하는지 여부를 판단하는 방법을 공부했다. 나누기 게임은 Alice와 Bob이 번갈아 가며 숫자 `n`을 선택된 약수로 나누고, 가장 먼저 숫자를 1로 만드는 사람이 승리하는 게임이다. 이 문제를 통해 Alice가 승리할 수 있는지 여부를 판단하는 방법을 배웠다.

### 어떤 문제가 있었고, 나는 어떤 시도를 했는지

주어진 문제는 숫자 `n`이 주어졌을 때, Alice가 항상 승리할 수 있는지 여부를 판단하는 것이었다. 이를 위해 숫자가 짝수일 때와 홀수일 때의 특성을 분석하고, 간단한 수학적 접근을 시도했다.

### 어떻게 해결했는지

가장 간단하고 효율적인 방법은 숫자가 짝수일 때 Alice가 항상 승리하고, 홀수일 때 Bob이 승리한다는 규칙을 이용하는 것이다. 이를 통해 문제를 해결할 수 있었다.

```python
class Solution:
    def divisorGame(self, n: int) -> bool:
        return n % 2 == 0
```

이 코드는 다음과 같은 방식으로 작동한다.

숫자 `n`이 짝수이면 `True`를 반환하고, 그렇지 않으면 `False`를 반환한다.
Alice는 항상 짝수로 시작할 경우 이길 수 있고, 홀수로 시작할 경우 질 수밖에 없다는 게임 이론적 특성을 활용한다.

### 무엇을 새롭게 알았는지

이번 문제를 해결하면서 간단한 수학적 규칙을 이용해 게임의 승패를 예측할 수 있는 방법을 배웠다. 특히, 짝수와 홀수의 특성을 이용하여 문제를 효율적으로 해결할 수 있었다. 이를 통해 파이썬에서 조건문을 활용한 문제 해결 능력을 향상시킬 수 있었다.

### 내일의 학습 계획

이번 문제와 유사한 게임 이론 문제를 더 풀어보는 것을 계획하고 있다. 예를 들어, 다른 유형의 게임 문제나, 전략을 이용한 최적의 플레이 방식을 찾는 문제를 해결해 볼 예정이다. 이를 통해 알고리즘 문제 해결 능력을 더욱 향상시키고자 한다.
