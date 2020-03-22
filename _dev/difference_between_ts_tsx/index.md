---
layout: post
title: ".ts .tsx 차이점은 무엇일까"
subtitle: "typescript"
type: "Typescript"
blog: true
text: true
author: "Cindy Cheon"
post-header: true
header-img: "img/header.jpg"
order: 8
---

이번에 새로 맡게 될 프로젝트는 react + typescript 를 써서 공부를 하던 중 프로젝트 코드를 살펴보니 `*.ts` 또는 `*.tsx` 파일로 있었고 굳이 왜 파일 확장자가 다를까 궁금해져서 검색을 해보았다.<br>


검색 결과를 간단하게 말하자면

`*.ts` 는 순수 typescript

`*.tsx` 는 React 의 모든 JSX (JavaScript XML) 를 지원한다는 것

**즉, *.ts는 JSX를 지원하지 않기 때문에 React component를 사용 하기 위해선 *.tsx를 써야 한다.**

<br>
🤔 *.ts에 JSX를 쓰게 되면 어떻게 될까?

```
testTs.ts

import * as React from "react";

export default function testTS() {
  return (
    <div>
      <h1>test</h1>
    </div>
  );
}

SyntaxError
/src/testTS.ts: Unterminated regular expression (6:16)

  4 |   return (
  5 |     <div>
> 6 |       <h1>test</h1>
    |                 ^
  7 |     </div>
```

결과는 SyntaxError가 난다.

```
// 변수 bar의 타입을 foo라고 선언
var foo =<foo>bar;

*.ts -> ok
*.tsx -> error
```

알고 보니 typescript는 타입을 지정해 줄 때 위와 같이 <> 로 지정해 주는데 이때 React를 Component를 사용하게 되면 JSX의 마크 <> 와 충돌하게 된다. 이런 문제점을 없애기 위해서 `*.tsx`가 나오게 되었다 🎉

번외로 위에 코드를 *.tsx에서 작성하게 되면 에러가 난다. `*.ts` 와 `*.tsx` 에서 모두 허용되는 as 문법( `var foo = bar as foo` )을 추가했다고 한다.
