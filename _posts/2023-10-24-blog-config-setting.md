---
published: true
title: Github 블로그 환경 세팅
date: 2023-10-24
categories: [Blog]
tags: [Blog, Homebrew, Ruby]
toc: true
toc_sticky: true
toc_label: "블로그 환경 세팅"
---

<img alt="github-logo" src="https://blog.kakaocdn.net/dn/Kl0e8/btqCzADnGSi/fC7tMdoSp6oGS8L2K429V1/img.png" >

> 개발을 하다가 복습 겸 정리를 위해서 블로그를 작성하기로 마음먹었다. <br>
> velog와 Tstory도 있었지만 1일 1잔디를 목표로 하고 있는 중이라서 어차피 자주 들어가는거 블로그도 깃허브로 작성해보자 하고 블로그를 만들기 시작했다. <br>
> 나는 이것저것 삽질을 했기에 이 글을 읽는 사람들은 좀 더 편하게 만들 수 있길 바란다.

## Home brew

Homebrew는 맥이나 리눅스 시스템에서 제공하는 패키지 관리자다. 개발을 조금이라도 접해봤다면 설치되어있겠지만 없다는 가정하에 처음부터 설치해보자

```shell
$ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

위 명령어를 입력하고 계정 비밀번호를 입력하면 멋지게 설치해줄 것이다.

잘 설치되었는지 확인해보고싶다면

```shell
$ brew -v
Homebrew 4.1.16
```

을 통해서 확인 할 수 있다.
[Homebrew 공식 사이트](https://brew.sh/ko/) 이동하기

## Ruby

나는 루비를 설치하려고 하니까 이미 설치되어 있었다. 아마 ReactNative를 사용하면서 설치했던 것 같다.
맥은 rbenv를 사용해서 루비를 설치하는데, 버전관리를 할 수 있도록 도와주는 것 같다.

```shell
$ brew install rbenv ruby-build
```

위 명령어를 통해서 필요한 플러그인을 설치한다.

```shell
$ rbenv install -l
$ rbenv install {설치 할 버전 ex. 3.2.2}
$ rbenv global {아까 입력한 버전}
```

위 명령어로 설치 할 수 있는 버전을 확인하고 설치한다. <br>
설치한 버전을 사용하도록 입력까지 같이 해준다.

[Ruby 공식 사이트](https://www.ruby-lang.org/en/) 이동하기

## PATH 설정

다음 스텝에서 진행할 과정에 선행되어야하는 작업이다. 뭐 설치 안 될때 경로 변경해주는 작업이다.

```shell
$ vi ~/.zshrc
```

위 명령어로 `zshrc` 파일에 접근한다. `i`를 누르면 편집모드에 접근 할 수가 있다. 편집모드에서 제일 밑 줄에 경로 설정을 추가해준다.

```shell
export PATH={$Home}/.rbenv/bin:$PATH && \
eval "$(rbenv init -)"
```

입력을 했다면 `esc`를 눌러 다시 원래 모드로 나와주고 `:wq`를 눌러서 파일에서 나와준다.

```shell
$ source ~/.zshrc
```

변경한 설정을 적용시키는 명령어를 입력해준다.

## 마무리

이제 필요한 환경 세팅은 끝났다. 아마 개발을 한다면 한번씩은 해야하는 작업들이니 귀찮더라도 세팅해주면 좋다.
다음에는 깃허브 블로그를 만들고 `Jekyll` 테마를 사용하여 예쁘게 꾸며보는 작업을 해보자.

### 다음 포스팅

> [Github 블로그 만들기 [1]](https://dev-woody.github.io/posts/make-github-blog-01/) <br> [Github 블로그 만들기 [2]](https://dev-woody.github.io/posts/make-github-blog-02/)
