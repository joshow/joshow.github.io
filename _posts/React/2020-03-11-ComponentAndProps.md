---
layout: post
title:  "React - Component와 Props"
date:   2020-03-11 13:00:00 +9000
category: [ React ]
tags: [ React, Javascript ]
---

## Component
React는 UI를 컴포넌트라는 단위로 구성한다. 이는 UI의 부분부분을 개별적인 조각으로 나눈 것이며 컴포넌트를 정의하여 사용할 시 다음과 같은 장점이 있다.
- 가독성이 좋아진다.
- UI를 재사용하기 용이하다.
- 유지보수가 쉬워진다.

<br>
개념적으로 컴포넌트는 자바스크립트의 함수이다.
```
function MyComponent(props) {
  return <h1>Component Name : {props.name}</h1>;
}
```
함수를 통해 JSX 표현식을 반환해주는 방식. 이를 “함수 컴포넌트”라 칭한다.

<br>
ES6에 도입된 클래스를 사용할 수도 있다.
```
class MyComponent extends React.Component {
  render() {
    return <h1>Component Name : {props.name}</h1>;
  }
}
```
React의 관점으로 봤을 때 위의 두 유형의 컴포넌트는 동일하다.

<br>
## Props
사용자 정의 컴포넌트는 결과적으로 JSX 표현식을 반환하기 때문에 React.render() 를 호출하여 렌더링할 수 있다.
이 때 React는 컴포넌트의 속성(Attribute)을 props라는 단일 객체에 담아 전달한다.
우리는 이 props를 사용하여 각 컴포넌트마다 내용을 다르게 구성할 수 있다.

```
// 위 코드에서 아래와 같이 표현식을 나타내면 다음과 같은 결과를 볼 수 있다.
element = <MyComponent name=“joshow”></MyComponent>
React.render(element, document.getElementById(‘root’);
```
# Component Name : joshow

<br>
props는 읽기 전용이기에 React의 컴포넌트들은 매개변수로 들어온 props 를 수정해서는 안된다.(순수함수)

이것은 React에서 매우 엄격한 규칙이다.

**[ All React components must act like pure functions with respect to their props. ]**

<br>
마지막으로 주의해야할 점은 모든 컴포넌트는 대문자로 시작한다.(Capitalize)
위에 작성한 컴포넌트의 이름을 myComponent 처럼 작성해선 안된다.
React는 소문자로 작성된 태그들을 모두 html 태그로 생각하기 때문에 div 같은 기본 태그는 사용해도 상관없으나 사용자지정 컴포넌트를 소문자로 작성하면 문제가 생긴다.

<br>
아무튼 이런 유용한 컴포넌트 기능을 이리저리 지지고 볶다보면 내가 원하는 UI를 작성할 수 있을 것이다.

<br>
[ 출처 : <https://ko.reactjs.org/docs/components-and-props.html> ]