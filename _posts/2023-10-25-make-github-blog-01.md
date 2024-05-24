---
published: true
title: Github 블로그 만들기 [1]
date: 2023-10-25
categories: [Blog]
tags: [Blog, Jekyll]
toc: true
toc_sticky: true
toc_label: "Github 블로그 만들기"
---

### 이전 포스팅

> [환경 세팅하기](https://dev-woody.github.io/posts/blog-config-setting/)

---

<img alt="jekyll-logo" src="https://github.com/dev-woody/dev-woody.github.io/assets/87690037/3f6d38a6-899e-489c-8797-e955b00ddd7f" >

> 개발 기술 블로그를 위한 깃허브 블로그 작성법이다. <br>
> M1 맥북을 기준으로 작성되었다. <br>

## Jekyll 설치하기

저번 포스팅에 맞춰 환경 세팅을 했다면 바로 이어서 `Jekyll`과 `bundler`를 설치해보자 <br>

터미널을 열어서 아래 명령어로 설치를 한다.

```shell
$ gem install jekyll

$ gem install bundler
```

버전 확인으로 설치가 잘 되었는지 확인한다.

```shell
$ jekyll -v
jekyll 4.3.2

$ bundler -v
Bundler version 2.4.10

```

## 깃허브 레퍼지토리 생성하기

깃허브 홈페이지로 이동해서 새로 레퍼지토리를 생성해준다.
녹색의 `New` 버튼을 누르면 된다.

<img alt="github-reposittories" src="https://github.com/dev-woody/dev-woody.github.io/assets/87690037/9df203bc-62ce-425b-b412-90f1764bb17f" >

레퍼지토리의 이름은 `{본인 깃허브 아이디}.github.io`로 작성해준다.
그래야 블로그로 쓸 수 있다. <br>
공개범위는 Public에 그대로 두고 생성하면 된다. 다른 설정 안 만져도 된다.

<img width="725" alt="github" src="https://github.com/dev-woody/dev-woody.github.io/assets/87690037/0e830311-29fe-4b6c-9061-7546b70ceb9f">

생성했으면 레퍼지토리에 들어가서 Code라고 쓰여있는 버튼을 눌러 HTTPS 밑에 쓰여있는 주소를 복사해주자<br>
그리고 데스크탑에 폴더를 하나 만들어서 터미널로 열고 깃허브 명령어를 입력해준다.

```shell
$ git init # 초기화
$ git clone {아까 복사한 주소}
```

그러면 생성한 폴더에 레퍼지토리 이름으로 된 폴더가 하나 더 생겼을 것이다.
이어서 Jekyll의 기본 번들을 설치를 하면 된다.

```shell
$ jekyll new ./
```

## 로컬서버 구동하기

이제 로컬서버에 블로그를 구동하여보자. 하단의 명령어를 입력하여 실행시킨다.

```shell
$ bundle exec jekyll serve
```

http://127.0.0.1:4000/ 을 브라우저에 입력해서 <br>
`Welcome to jekyll!` 이 잘 나타나는 지 확인한다.

확인했다면 `Cmd + C`로 서버를 닫아준다.

이제 테마를 다운받아서 적용해보자.

## 테마 적용하기

매우 다양한 Jekyll 테마가 있기에 본인이 마음에 드는 테마를 적용하면 된다.<br>
테마 모음사이트도 다양하니 더 찾아보거나 아래 주소로 찾아보면 된다.

[jamstackthemes.dev](https://jamstackthemes.dev/ssg/jekyll/)

[jekyllthemes.io](https://jekyllthemes.io/)

[jekyll-themes.com](https://jekyll-themes.com/)

테마를 적용하는 방법은 3가지가 있는 것 같다.

1. [chirpy starter](https://github.com/new?template_name=chirpy-starter&template_owner=cotes2020) 로 적용하기 <br>
   설치 방법이 쉽고 편하다는 장정이 있지만 커스터마이징하기 어렵다는 문제가 있다.

2. [fork](https://github.com/cotes2020/jekyll-theme-chirpy) 받아서 적용하기 <br>
   초기 커스터마이징 설정이 필요하다. 나는 이 방법도 커스텀중에 문제가 생겨서 제일 마지막 방법을 사용하였다.

3. [zip](https://github.com/cotes2020/jekyll-theme-chirpy/archive/refs/heads/master.zip) 으로 받아서 적용하기 <br>
   fork로 설치하게 되면 나중에 댓글이나 다른 여러 기능을 추가할때 문제가 생길 수도 있다. <br>
   초기에 설정해주면 된다고 하지만 찾아보기도 귀찮고 어떤걸 설정해야하는지 몰라서 그냥 zip파일을 받아서 했다.

나는 블로그 작성하기에 편하고 사람들이 많이 쓰는 테마로 설치를 했다. 같은 테마를 적용하고 싶다면 위의 링크로 다운받아서 사용하면 된다. <br>
깃허브에서 받아도 되고 테마 모음 사이트에서 받아도 무관하다.

다운받은 파일을 `github.io` 폴더에 복사 붙여넣기한다. 중복되는 파일은 모두 대치시키면 된다.

다운받은 테마를 초기화해준다.

- Gemfile.lock 파일 삭제
- .travis.tml 파일 삭제
- \_posts 디렉토리 삭제
- docs 디렉토리 삭제
- .github/workflows/pages-deploy.yml.hook 파일을 제외한 나머지 파일 삭제
- .github/workflows/pages-deploy.yml.hook 파일명을 pages-deploy.yml로 변경

이제 파일을 깃허브에 올리면 된다.

```shell
$ bundle install # 테마 적용하기
$ npm install && npm run build
# 페이지를 이동할때마다 콘솔에 파일을 찾을 수 없다는 콘솔이 떠서 npm으로 빌드를 하고나니 더 이상 콘솔에 에러가 뜨지않았다.

$ git add . # 파일 업로드
$ git commit -m "update-theme" # 커밋
$ git push # 깃허브에 푸시 (안된다면 git push --force 를 해보자)
```

깃 명령어는 나중에 따로 다루도록 하고 이제 본인아이디.github.io로 들어가면 테마가 적용된 것을 볼 수 있다.

<img width="2230" alt="Chirpy-demo" src="https://github.com/dev-woody/dev-woody.github.io/assets/87690037/3fc72fab-b912-4ee8-a7dc-90c1b9a3d5ba">

## 마무리

드디어 테마 적용까지 끝났다. 이제 블로그 설정 변경과 포스팅하기만 다루면 자유롭게 블로그를 쓸 수 있다. <br>
블로그 만들기 포스팅이 끝나면 마크다운 작성법이나 댓글같은 추가 기능 적용법도 업로드 할 예정이다. <br>
블로그 작성을 하려는 사람들에게 조금이나마 도움이 됐으면 좋겠다.

### 다음 포스팅

> [Github 블로그 만들기 [2]](https://dev-woody.github.io/posts/make-github-blog-02/)
