---
published: true
title: Github 블로그 댓글연동
date: 2023-12-07
categories: [Blog]
tags: [Blog, utternaces, chirpy]
toc: true
toc_sticky: true
toc_label: "블로그 댓글 연동"
---

<img width="769" alt="utternace" src="https://github.com/dev-woody/dev-woody.github.io/assets/87690037/945e2b32-9967-45a7-9dcc-e2a2fe3a7881">

> 개인적인 사정으로 블로그 관리를 한달정도 하지 못 했다.. <br>
> 연말이기도 하니까 유종의 미를 거둔다는 생각으로 다시 열심히 작성해보려고 한다.<br>
> 따라서 블로그의 꽃인 댓글 기능을 한번 연동해보자!!

## Utternace

지금까지 내가 작성한 글을 따라서 블로그를 만들었다면 댓글 연동하는 방법은 쉬울 것이다.

Chirpy 테마를 사용하면 기본적인 세팅은 다 되어있는데 일단 root에 있는 `_config.yml` 로 이동해보자.

comments 를 컨트롤이나 커맨드 + f 로 찾아서 하단 이미지와 같은 내용이 있는지 확인한다.

<img width="467" alt="comments" src="https://github.com/dev-woody/dev-woody.github.io/assets/87690037/dc1606d4-b225-42a0-8de9-69c22f95bbcd">

active를 `utternaces`로 입력해주고 밑에 repo를 본인의 깃허브네임과 블로그 주소를 넣어준다.

issue_term은 title로 해두자. utternace는 깃허브 repo에 이슈로 댓글을 작성해주는데 이를 확인하기 쉽게하기 위해서 title로 설정해놓으면 어떤 글에 댓글이 달렸는지 확인하기 쉽다.

## Setting

위에서 repo를 본인의 깃허브 블로그로 설정했을 것이다. 이제 본인의 repo에 설치를 하면 된다.

[utternaces 설치 링크](https://github.com/apps/utterances)

위 링크로 들어가면 하단과 같은 사이트에 들어가질텐데 난 이미 설치해서 Configure이라고 되어있지만 원래는 우측 버튼이 녹색으로 install 이라고 되어있을 것이다. 클릭해서 설치를 진행해보자.

<img width="1053" alt="utternaces install" src="https://github.com/dev-woody/dev-woody.github.io/assets/87690037/a5d43193-42e4-4a2b-b355-f63314169dcc">

클릭하면 redio 버튼이 두개가 보일텐데 하단의 `Only select repositoryies`를 클릭하자. 그러면 select box가 나오면서 본인의 깃 저장소가 나오는데 블로그를 선택해주자.

그러면 밑에 install 버튼이 활성화됐을 것이다. 클릭해서 설치하자.

이후에 화면이 이동하면서 적용방법을 알려주지만 우리의 친절한 chirpy 테마는 이미 적용을 해놓았기 때문에 따로 작업을 하지않아도 된다. 다크모드도 알아서 잘 지원해준다.

이제 블로그를 확인해보면 하단과 같은 댓글이 생겼을 것이다.

<img width="824" alt="comments" src="https://github.com/dev-woody/dev-woody.github.io/assets/87690037/2f1d4c55-fb7a-4489-ba97-c98b3b165e0b">

## 마무리

다른 블로그의 댓글 연동보다 쓸 말이 없어서 작성하고나니 초라해보인다는 생각이 든다. 하지만 테마에서 다 지원해줘서 할게 없는걸...

chirpy테마를 사용하지 않는 분이나 스크립트로 적용하는게 궁금한 분은 아래 링크에서 확인하시면 될 것 같다.

### 참조

[하얀눈길님의 블로그 Jekyll 테마에 utterances 댓글 연동하기](https://www.irgroup.org/posts/utternace-comments-system/)

[utternaces 사이트](https://utteranc.es/)
