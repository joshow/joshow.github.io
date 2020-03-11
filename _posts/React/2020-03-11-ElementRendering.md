---
layout: post
title:  "React - 엘리먼트 렌더링"
date:   2020-03-11 12:00:00 +9000
category: [ React ]
tags: [ React, Javascript ]
---

### 엘리먼트 렌더링
React로 구성된 일반적인 앱들은 하나의 Root DOM 을 가진다.
```
<div id="root"></div>
```

<br>

물론 경우에 따라 독립된 Root DOM 을 여러개 가질 수도 있다.(기존 웹페이지 부분부분 리액트 앱을 추가하는 경우 / id가 꼭 root일 필요는 없다.)

<br>
ReactDOM.render() 를 호출하여 원하는 Root DOM 에 렌더링 하려면 아래와 같이 코드를 작성하면 된다.
```
ReactDOM.render(<React 엘리먼트>, <Root DOM 객체>)
// ReactDOM.render(element, document.getElementById(‘root’));
```

<br>

[ 출처 : <https://ko.reactjs.org/docs/rendering-elements.html> ]

