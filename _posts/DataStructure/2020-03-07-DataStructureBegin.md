---
layout: post
title:  "자료구조 공부 시작"
date:   2020-03-07 14:00:00 +9000
category: [ 자료구조 ]
tags: [ 자료구조 ]
---

### 자료구조란?
컴퓨터에서 여러 데이터를 조직적, 체계적으로 저장하는 방식을 통틀어 말한다. 각 자료구조들은 자기들만의 일정한 규칙을 가지며 데이터를 저장한다. 배열 또한 변수가 나열된다는 규칙을 가진 자료구조의 일종이다.

<br>

### 왜 필요할까?
별도의 자료구조가 필요한 이유는 메모리 공간을 보다 효율적으로 사용하여 데이터를 저장하거나 특정 알고리즘을 수행시 속도 향상 등의 이유가 있겠지만 주관적인 생각으론 그냥 내가 쓰기 편해서 쓰는 것 같다. 여러 변수들이 죄다 다른 주소로 산개되어 있는 것보다 배열 하나로 쭈르륵 있는게 변수명 외우기도, 수정하기도, 사용하기도 더 쉽지 않겠는가? 아무튼 자신의 필요에 따라 적절한 자료구조를 선택 한다면 더 높은 성능의 프로그램을 구현하거나 복잡한 로직 없이 편-안하게 프로그래밍을 할 수 있을 것이다.

<br>

### 왜 공부하는가?
최근 고급? 프로그래밍언어(파이썬이나 자바스크립트 등)들을 보면 간단한 자료구조들은 이미 다 구현이 되어있다. 그냥 가져다가 쓰면 성능 좋고 편하다! 근데 대체 왜 배울까? 우선 나는 앞으로도 C 프로그래밍을 계속 하게될 것 같다. 근데 그런 성능 좋고 편한 자료구조가 C에는 없다. 배우는건 필연적이다. 그 외에도 여러가지 있다. 고수준의 프로그래밍 언어(다루기 쉬운)에서 동작하는 방식이 어떤 원리로 돌아가는지가 궁금하고, 실제로 포인터와 자료구조를 다시 공부하면서 아 파이썬의 리스트는 내부적으로 이런이런 방식으로 돌아가겠구나 (실제로 얼마나 맞을진 확신할 수 없지만) 같은 깨달음을 얻을 수도 있었다. 지금 하는 공부는 그러한 식견을 넓히는데 도움이 되리라 믿는다. 또 남들이 만든 것만 쓰다가는 아무도 것에도 도움 받을 수 없는 상황이 왔을 때 이를 해결할 수 없게되지 않을까란 생각도 크다. 물론 적절한 라이브러리의 활용은 개발자들에게 중요한 자질이고 나는 그에 좀 더 익숙해질 필요가 있겠지만 -_-;; 그건 좀 나중에 ㅎㅎ

<br>

여러 사설들이 있었지만 아무튼 열심히 공부해보고 그 내용과 직접 작성한 소스들을 포스팅할 계획이다.