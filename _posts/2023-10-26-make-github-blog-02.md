---
published: true
title: Github 블로그 만들기 [2]
date: 2023-10-26
categories: [Blog]
tags: [Blog, Jekyll]
toc: true
toc_sticky: true
toc_label: "Github 블로그 만들기"
---

### 이전 포스팅

> [환경 세팅하기](https://dev-woody.github.io/posts/blog-config-setting/) <br> [Github 블로그 만들기 [1]](https://dev-woody.github.io/posts/make-github-blog-01/) <br>

---

<img alt="github" src="https://github.com/dev-woody/dev-woody.github.io/assets/87690037/d244244e-35ed-4480-b6d9-c1fcc5099e90" >

> 개발 기술 블로그를 위한 깃허브 블로그 작성법이다. <br>
> M1 맥북을 기준으로 작성되었다. <br>

## Jekyll 커스터마이징

이제 본인정보에 맞춰서 설정만 변경하면 개인 블로그가 생성된다.

<img width="524" alt="config" src="https://github.com/dev-woody/dev-woody.github.io/assets/87690037/c981ec5e-2813-4c9e-9eed-e0f2d53e92e9">

### \_config.yml

\_config.yml을 열어서 변경하면된다. 수정 후 로컬서버는 재구동해주자.

| 키                       | 값                            | 설명                                                                                                                                                        |
| ------------------------ | ----------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| lang                     | ko                            | 언어설정이다. 어떤 언어를 쓸 수 있는지는 \_data.locales에서 확인 가능하다.                                                                                  |
| timezone                 | Asia/Seoul                    | 시간 설정이다. 서울로 해두자.                                                                                                                               |
| title                    | 타이틀                        | 블로그 이름이다.                                                                                                                                            |
| tagline                  | 부타이틀                      | 이름 밑에 들어가는 작은 설명이다.                                                                                                                           |
| description              | 설명                          | SEO에 적용되는 키워드다. 검색 필터에 적용된다고 생각하면 된다.                                                                                              |
| url                      | "https://dev-woody.github.io" | 블로그에 접속될 URL이다.                                                                                                                                    |
| google_site_verification | 나중에 설정                   | 구글 검색 노출 설정이다. 추후에 추가할것이다.                                                                                                               |
| google_analytics         | 나중에 설정                   | 방문자 조사같은거다. 어떤 경로로 어느 페이지에 있는지 알 수 있다.                                                                                           |
| img_cdn                  | ""                            | 이미지의 루트 경로같다. \_post 폴더를 지우지 않았다면 비우지말자. 깃허브에 푸시해도 적용이 안된다. 폴더를 지웠다면 비워두자. 그래야 프로필 이미지가 보인다. |
| avatar                   | 프로필 이미지                 | 프로필에 설정되는 이미지다. 보통 "/assets/img/"에 넣어둔다.                                                                                                 |

## 포스팅하기

이제 글을 작성하자. 루트에 `_post` 폴더를 만들고 그 안에 마크다운 파일을 만든다.

파일이름은 `YYYY-MM-DD-{블로그-제목}.md` 형식으로 작성한다.

```markdown
---
title: 포스팅 제목
date: YYYY-MM-DD HH:MM:SS +09:00
categories: [카테고리, 2차 카테고리]
tags: [태그, 태그]
toc: true
toc_sticky: true
toc_label: "목차 제목"
---
```

위의 내용을 기본으로 입력해주고 이후는 마크다운 작성법에 맞춰서 작성해주면 된다.<br> 마크다운 작성법은 추후에 다루도록하자.

글을 생성하면 다시 깃허브에 올려준다.

```shell
$ git add .
$ git commit -m "커밋 명"
$ git push
```

## 마무리

개인 설정까지 끝내면서 블로그 만들기가 마무리됐다. <br>
이후에 마크다운 작성법과 댓글 기능이나 검색 노출, 광고 설정 등의 추가적인 내용들도 다룰 예정이다. 그리고 새로 블로그를 개설하려는 사람들은 에러없이 쉽게 작성하길 바라는 마음에 내가 블로그를 개설하면서 겪었던 에러들도 모아서 작성하려고 한다. 다들 기술 블로그도 작성하면서 개발자 갓생을 살아보자!
