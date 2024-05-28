---
published: true
title: Nextjs14 업데이트
date: 2023-10-30
categories: [Nextjs]
tags: [Nextjs, frontend, Reactjs]
toc: true
toc_sticky: true
toc_label: "Nextjs14 업데이트"
---

<img alt="nextjs" src="https://github.com/dev-woody/dev-woody.github.io/assets/87690037/e01f582e-fbb6-4474-acc0-91203119af83" />

> nextjs 14 버전이 업데이트되었다. 작년에 13버전이 업데이트되고 app router나 여러 기능들을 배우느라 정신없었는데 벌써 1년이 지나서 14버전이라니.. 시간 참 빠르다. 무엇이 바뀌었는지 한번 알아보자.

## Turbopack

Next.js 14는 Rust기반 엔진인 Turbopack을 사용한다. 13에서도 이를 사용해서 속도가 빨라졌다 했는데, 이번 업데이트는 무려 로컬에서 `53%` 빠른 시작과 `94%` 빠른 코드 업데이트 성능을 보여준다고한다.

## Server Actions

블로그를 보면 Nextjs 9부터 api router를 지원한다고 되어있다. 이번에는 전용 API 경로없이 서버 코드를 트리거 할 수 있다고한다.

예시로 다음과 같은 코드를 제공한다.

```js
export default function Page() {
  async function create(formData: FormData) {
    "use server";
    const id = await createItem(formData);
  }

  return (
    <form action={create}>
      <input type="text" name="name" />
      <button type="submit">Submit</button>
    </form>
  );
}
```

설명을 하자면 이전에 api 폴더에 서버역할을 하는 코드를 작성하고 프론트단에서 호출하는 방식이였는데 이젠 그냥 프론트에서 db랑 소통한다고 보면 된다. php를 사용해본 개발자라면 옛날 php처럼 되는구나 하고 생각하면 될 것 같다.

**덕분에 이런 밈도 돌고 있다.**
<img alt="nextjs14" src="https://github.com/dev-woody/dev-woody.github.io/assets/87690037/43decc30-b322-4725-babf-5463761d4f0f" />

## Partial Prerendering

이건 아직 정식은 아닌 것 같지만 SSR과 SSG의 지속적 검토로 두 방식의 이점만 제공한다고 되어있다.

그리고 추가로 react의 Suspense를 기반으로 정적 사이트의 성능개선과 서버 랜더링의 역동성을 얻을 수 있다고 한다.

## Metadata Improvements

`viewport`,`colorScheme`그리고 `themeColor`와 같은 metadata 옵션은 초기 페이지 내용과 함께 전송되어 사용자 환경을 원활하게하여 테마 색상을 변경하거나 뷰포트 변경으로 인해 레이아웃을 이동하여 페이지가 깜박 거리지 않도록한다.

## 마무리

이번에 업데이트 되었다고해서 또 13때처럼 많이 바뀌면 어쩌지 걱정했는데 그런건 없어서 다행이다.<br>
성능적으로 많이 개선되고 점점 더 편하게 사용 할 수 있게 되어서 마음에 든다.<br>
자세한 블로그 내용은 하단 링크를 참조해서 보면 좋을 것 같다.<br>
[Nextjs14 공식 문서](https://nextjs.org/blog/next-14) <br>
[Nextjs Keynote](https://nextjs.org/conf?source=post_page-----c49f9167b7c3--------------------------------) <br>
[14개의 챕터로 배우는 Nextjs](https://nextjs.org/learn?source=post_page-----c49f9167b7c3--------------------------------)
