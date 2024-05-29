---
published: true
title: 99클럽 코테 스터디 10일차 모의고사
date: 2024-05-29
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

## [오늘의 문제 : 모의고사](https://school.programmers.co.kr/learn/courses/30/lessons/42840)

#### 문제 설명

수포자는 수학을 포기한 사람의 준말입니다. 수포자 삼인방은 모의고사에 수학 문제를 전부 찍으려 합니다. 수포자는 1번 문제부터 마지막 문제까지 다음과 같이 찍습니다.

1번 수포자가 찍는 방식: 1, 2, 3, 4, 5, 1, 2, 3, 4, 5, ...<br>
2번 수포자가 찍는 방식: 2, 1, 2, 3, 2, 4, 2, 5, 2, 1, 2, 3, 2, 4, 2, 5, ...<br>
3번 수포자가 찍는 방식: 3, 3, 1, 1, 2, 2, 4, 4, 5, 5, 3, 3, 1, 1, 2, 2, 4, 4, 5, 5, ...

1번 문제부터 마지막 문제까지의 정답이 순서대로 들은 배열 answers가 주어졌을 때, 가장 많은 문제를 맞힌 사람이 누구인지 배열에 담아 return 하도록 solution 함수를 작성해주세요.

#### 제한 조건

- 시험은 최대 10,000 문제로 구성되어있습니다.
- 문제의 정답은 1, 2, 3, 4, 5중 하나입니다.
- 가장 높은 점수를 받은 사람이 여럿일 경우, return하는 값을 오름차순 정렬해주세요.

## 학습 키워드

- 리스트 순회
- 패턴 매칭
- 최댓값 찾기

## 오늘의 회고

### 공부한 내용 본인의 언어로 정리하기

이번 문제에서는 정답 리스트와 학생들의 답안 패턴을 비교하여 가장 많은 정답을 맞춘 학생을 찾는 방법을 공부했다. 이를 위해 파이썬의 리스트 순회와 패턴 매칭을 활용했다. 특히, 반복 패턴을 사용하여 정답을 맞춘 학생을 찾는 방법과 최댓값을 찾아 가장 많은 정답을 맞춘 학생을 구하는 방법을 배웠다.

### 어떤 문제가 있었고, 나는 어떤 시도를 했는지

주어진 문제는 정답 리스트와 학생들의 답안 패턴을 비교하여 가장 많은 정답을 맞춘 학생을 찾는 것이었다. 이를 위해 각 학생의 답안 패턴을 반복적으로 비교하고, 정답을 맞춘 횟수를 계산하는 방법을 시도했다. 또한, 최댓값을 찾아 가장 많은 정답을 맞춘 학생을 리스트에 추가하는 방법도 시도했다.

### 어떻게 해결했는지

가장 간단하고 효율적인 방법은 주어진 정답 리스트와 각 학생의 패턴을 비교하여 정답을 맞춘 횟수를 계산하고, 가장 많은 정답을 맞춘 학생을 찾아 리스트에 추가하는 것이었다. 이를 통해 문제를 해결할 수 있었다.

```python
def solution(answers):
    def solution(answers):
    answer = []

    means1 = 0
    means2 = 0
    means3 = 0

    num1 = [1, 2, 3, 4, 5]
    num2 = [2, 1, 2, 3, 2, 4, 2, 5]
    num3 = [3, 3, 1, 1, 2, 2, 4, 4, 5, 5]

    student1 = []
    student2 = []
    student3 = []

    for i in answers :

        if i == num1[means1] :
            student1.append(i)

        if i == num2[means2] :
            student2.append(i)

        if i == num3[means3] :
            student3.append(i)

        means1 += 1
        means2 += 1
        means3 += 1

        if means1 > 4 :
            means1 = 0

        if means2 > 7 :
            means2 = 0

        if means3 > 9 :
            means3 = 0

    maxNum = max([len(student1), len(student2), len(student3)])

    if maxNum == len(student1) :
        answer.append(1)

    if maxNum == len(student2) :
        answer.append(2)

    if maxNum == len(student3) :
        answer.append(3)



    return answer
```

이 코드는 주어진 정답 리스트와 각 학생의 패턴을 비교하여 정답을 맞춘 횟수를 계산한다. 각 학생의 패턴은 리스트의 길이로 나눈 나머지를 사용하여 반복적으로 비교된다. 이후, 가장 많은 정답을 맞춘 학생을 찾아 리스트에 추가한다.

### 무엇을 새롭게 알았는지

이번 문제를 해결하면서 반복 패턴을 사용하는 효율적인 방법을 배웠다. 이를 통해 리스트의 특정 조건을 만족하는 값을 찾고, 이를 비교하여 최댓값을 찾는 과정을 배웠다. 또한, 조건문을 활용하여 리스트 비교 및 최댓값 찾기의 중요성도 깨달았다. 이를 통해 파이썬에서 리스트를 다루는 다양한 기법을 익히게 되었다.

아무리 생각해도 좋은 문제풀이는 아니기에 챗 지피티한테 물어봤다.

#### 챗지피티의 풀이

```python
def solution(answers):
    patterns = [
        [1, 2, 3, 4, 5],
        [2, 1, 2, 3, 2, 4, 2, 5],
        [3, 3, 1, 1, 2, 2, 4, 4, 5, 5]
    ]
    scores = [0, 0, 0]

    for i, answer in enumerate(answers):
        for j, pattern in enumerate(patterns):
            if answer == pattern[i % len(pattern)]:
                scores[j] += 1

    max_score = max(scores)
    return [i + 1 for i, score in enumerate(scores) if score == max_score]
```

이 코드는 정답과 패턴의 값을 순회하여 비교하고 같다면 스코어의 값을 1씩 올리는 행위를 반복한다. 그리고 정답 배열에 가장 높은 점수와 비교하여 같다면 정답 배열에 추가한다. 훨씬 깔끔하고 간결했고 반복문이 끝난 후에도 means나 student를 남기지 않아 효율적이였다.

아직 코딩의 세계는 갈길이 멀다는 것을 다시 한번 느꼈다.

## 내일의 학습 계획

enumerate에 대해서 알아보자!
