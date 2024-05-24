---
published: true
title: Markdown 마크다운 작성법
date: 2023-11-01
categories: [Blog]
tags: [Markdown, blog]
toc: true
toc_sticky: true
toc_label: "Nextjs14 업데이트"
---

### 이전 포스팅

> [환경 세팅하기](https://dev-woody.github.io/posts/%EB%B8%94%EB%A1%9C%EA%B7%B8-%ED%99%98%EA%B2%BD-%EC%84%B8%ED%8C%85/)<br> [Github 블로그 만들기 [1]](https://dev-woody.github.io/posts/M1-Mac-%ED%99%98%EA%B2%BD%EC%97%90%EC%84%9C-Github-%EB%B8%94%EB%A1%9C%EA%B7%B8-%EB%A7%8C%EB%93%A4%EA%B8%B0-1/) <br> [Github 블로그 만들기 [2]](https://dev-woody.github.io/posts/%EB%B8%94%EB%A1%9C%EA%B7%B8-%EB%A7%8C%EB%93%A4%EA%B8%B0-2/)

---

<img alt="markdown" src="https://github.com/dev-woody/dev-woody.github.io/assets/87690037/c4ca58cc-d6c3-42e5-90ab-dbc2f368535f" />

> 마크다운 (Markdown)은 마크업 언어의 일종으로 읽기도 쓰기도 쉬운 문서 양식을 지향한다. `github의 README.md` 파일이 바로 마크다운으로 작성된 파일이다. 또 옵시디언이나 노션도 마크다운이니 예쁘게 작성하고싶다면 작성법을 익혀두자.

## 헤더 Header

```markdown
# H1

## H2

### H3

#### H4

##### H5

###### H6
```

H7은 지원을 안 하지만 이렇게하면 제목을 작성할 수 있다.

```markdown
# H1

## H2
```

H1과 H2는 이렇게도 작성할 수 있다.

## 인용문 Blockqute

```markdown
> 이렇게
>
> > 인용문을
> >
> > > 작성한다.
```

> 이렇게
>
> > 인용문을
> >
> > > 작성한다.

## 목록 List

```markdown
1. 순서가 있는 목록
2. 순서가 있는 목록
3. 순서가 있는 목록

- 순서가 필요하지 않은 목록
  - 대시(hyphen)
    - 별표(asterisks)
      - 더하기(plus sign)
```

1. 순서가 있는 목록
2. 순서가 있는 목록
3. 순서가 있는 목록

- 순서가 필요하지 않은 목록
  - 대시(hyphen)
    - 별표(asterisks)
      - 더하기(plus sign)

## 링크 Link

```markdown
[링크텍스트](링크)
[GOOGLE](https://google.com)

일반적인 링크 <https://google.com>
```

[GOOGLE](https://google.com) <br>
<https://google.com>

## 강조 Emphasis

```markdown
_이텔릭 효과_
_이텔릭 효과_
**볼드 효과**
**볼드 효과**
~~취소선 효과~~
```

_이텔릭 효과_ <br>
_이텔릭 효과_ <br>
**볼드 효과** <br>
**볼드 효과** <br>
~~취소선 효과~~ <br>

## 이미지 Image

```markdown
![image](이미지 링크)

사이즈 조절이 필요하면 이미지 태그를 쓰자
<img width="" height=""></img>

링크를 응용한다면 이미지에 링크를 걸 수 있다.
```

<img alt="blog-img" src="https://github.com/dev-woody/dev-woody.github.io/assets/87690037/43decc30-b322-4725-babf-5463761d4f0f" />

`링크 이미지` <br>
[<img alt="small-blog-img" src="https://github.com/dev-woody/dev-woody.github.io/assets/87690037/5657388f-6eae-4847-b49a-8c4630022083" width="200px" height="200px" />](https://dev-woody.github.io/)

## 코드 Code

<pre><code>
```js
// 이곳에 코드 작성
```
</code></pre>

```js
// 이곳에 코드 작성
```

## 표 Table

```markdown
| 번호 |   제목   |     내용 |
| ---- | :------: | -------: |
| 1    | 마크다운 | 배워보자 |
| 2    | 블로그를 |   위해서 |
```

| 번호 |   제목   |     내용 |
| ---- | :------: | -------: |
| 1    | 마크다운 | 배워보자 |
| 2    | 블로그를 |   위해서 |

## 수평선 Horizontal Rule

```markdown
---
(Hyphens)
---

(Asterisks)

---

(Underscores)
```

---

(Hyphens)

---

(Asterisks)

---

(Underscores)

## 줄 바꿈 Line Breaks

```js
글을 쓰다가 줄을 나누고 싶으면
// 띄어쓰기를 두번 하거나
원시태그인 `<br>`을 사용하면 된다.
```

글을 쓰다가 줄을 나누고 싶으면

띄어쓰기를 두번 하거나 <br>
원시태그인 `<br>`을 사용하면 된다.

## 마무리

기본만 적었지만 포스팅으로 이만큼 쓰는 것은 꽤 많은 양이였다. 그래도 이 정도 문법만 알아도 블로그를 작성하기에는 충분할 것이다. <br>
더 많은 문법을 알고싶다면 [마크다운 공식문서](https://www.markdownguide.org/)를 방문해보자.

이제 블로그도 작성할 수 있으니 다음에는 댓글과 같은 부가적인 기능들을 추가하는 법을 작성해보려고 한다. 다음 포스팅을 정리하는동안 마크다운도 더 찾아보고 블로그 쓰는 것에 더 익숙해져야겠다.
