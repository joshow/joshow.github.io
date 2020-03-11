---
layout: post
title:  "React - JSX 소개"
date:   2020-03-11 11:00:00 +9000
category: [ React ]
tags: [ React, Javascript, JSX ]
---

## JSX 소개
리액트는 JSX 라는 확장된 자바스크립트를 이용하여 코드를 작성할 수 있다.
일반적인 자바스크립트로도 가능하지만 JSX를 사용하여 UI 작업을 하였을 때 시각적으로 도움이 될 수 있다.

<br><br>

아래는 JSX 표현식을 사용한 예이다.
HTML에서 사용하는 태그 그 자체를 표현식으로써 사용할 수 있다.
```
const element = <h1>Hello, world!</h1>;
```

<br>

따라서 해당 태그 그대로 반환하는 것도 가능하다.
```
function func(){
	return <h1>Hello, world!</h1>;
}
```

<br>

JSX는 중괄호 안에 모든 유효한 자바스크립트 표현식을 넣을 수 있다.
```
const element = <div className = {user.name}></div>;
```

<br>

이러한 표현식은 자바스크립트 내부적으론 하나의 객체이며 이 객체를 **React 엘리먼트**라고 부른다.

순수 자바스크립트에서 JSX 표현식과 같이 React 엘리먼트를 만드려면 React.createElement()를 호출하면 된다.

자세한 설명은 [링크](https://reactjs-kr.firebaseapp.com/docs/react-api.html#createelement) 참조

<br>

## 바벨(Babel)
바벨은 트랜스파일러로 최신 버전의 자바스크립트 문법을 지원하지 않는 브라우저에서도 최신 문법을 사용할 수 있도록 작성한 코드에서 사용된 최신 문법들을 모든 브라우저가 지원하는 이전 문법에 맞게 코드를 수정하여 준다.

React 또한 내부적으로 바벨에서 JSX를 일반 자바스크립트로 코드를 변환해주기 때문에 사용 가능한 것이다.
많은 자바스크립트 프로젝트에서 사용된다고 하니 언젠가 숙지해두면 좋을듯

자세한 내용은 [링크](https://www.daleseo.com/js-babel/) 참조

<br>

[ 출처 : <https://ko.reactjs.org/docs/introducing-jsx.html> ]
