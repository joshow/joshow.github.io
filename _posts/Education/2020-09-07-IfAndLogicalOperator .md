---
layout: edu
title:  "if문과 논리 연산자"
date:   2020-09-07 10:30:00 +9000
category: [ Education ]
tags: [ Python, Education ]
---

- - - 
- - -
<br>

## [1. 배운 내용](#배운-내용)   
## [2. 숙제](#숙제)   
<br>
- - - 
- - -

<br>

# **배운 내용**
## **불(bool) 자료형**
파이썬에서 어떠한 값을 표현하는 방식으로 1234567890 으로 표현하는 숫자형과 따옴표(', ")로 문자들을 감싼 문자열형이 있었다.   
새로 소개할 불 자료형은 위의 두 자료형과 별개로 **참과 거짓**이라는 값을 표현하는 특별한 자료형이다.   
+ 참 - True
+ 거짓 - False

<br>

## **조건문 if**
``` python
# if문의 구조
if 조건문:
    True일 때 수행할 코드
    True일 때 수행할 코드
    True일 때 수행할 코드
else:
    False일 때 수행할 코드
    False일 때 수행할 코드
    False일 때 수행할 코드
```

if문은 프로그램은 상황에 따라 다른 동작을 해야하는 경우에 사용한다. if문과 같이 쓰여진 조건문이 **True**일 때 그 아래 코드가 실행되고, **False**라면 **else**에 해당하는 코드가 실행이 된다.(여기서 else문은 생략되어도 괜찮다.)   

친구들이 즐겨하던 서핑보드 게임을 예로 들어보면 게임을 시작하고 캐릭터는 힘차게 파도를 가르며 이동한다. 그런데 잘 이동하던 캐릭터가 장애물에 닿아 버리면 게임이 끝나고만다. 이러한 상황을 if문으로 표현하자면 아래와 같다.

``` python
if 캐릭터가 장애물에 닿았다:
    게임오버
else:
    계속해서 게임을 진행
```
여기서 게임을 막 시작했을 때는 '캐릭터가 장애물에 닿았다'라는 **조건문**이 False이기 때문에 else에 해당하는 코드가 실행된다. 하지만 캐릭터가 장애물을 만났을 때는 조건이 True가 되기 때문에 if문 안의 코드가 실행될 것이고 그 결과 게임이 끝나버리는 것이다.

<br>

## **비교 연산자**
그렇다면 조건문은 어떻게 표현할 수 있을까?   
파이썬에서는 수학시간에 볼 수 있던 '등호/부등호' 기호를 이용해 특정한 조건을 표현할 수 있으며 총 6가지의 비교 연산자가 있다.

|연산자|의미|
|---|---|
|a **>** b|a가 b보다 크다|
|a **<** b|a가 b보다 작다|
|a **>=** b|a가 b보다 크거나 같다|
|a **<=** b|a가 b보다 작거나 같다|
|a **==** b|a와 b가 같다|
|a **!=** b|a와 b가 다르다|

사칙연산자(+,-,*,/)가 계산의 결과가 있듯 비교 연산자도 비교한 결과 값이 나온다.   
그 결과 값은 **bool 자료형**의 형태로 나타난다.

``` python
3 + 5               # 결과는 8
7 < 6               # 결과는 False
"jiho" == "jiho"    # 결과는 True
```
<br>
우리는 이러한 비교 연산자를 통해 if문의 조건을 작성할 수 있다.
이에 대한 예시로 수업 시간에 함께 작성했던 성적 등급 판별 프로그램 코드를 남겨두겠다. 코드를 읽어보면 내용이 기억날거라 생각된다.

``` python
jumsoo = input("점수를 입력하세요: ")
jumsoo = int(jumsoo)

if jumsoo >= 90:
    print("A등급 입니다. 대단해요~")
elif jumsoo >= 80:
    print("B등급 입니다. 잘하시네요!")
elif jumsoo >= 70:
    print("C등급 입니다. 평범해요.")
elif jumsoo >= 60:
    print("D등급 입니다. 좀 더 노력해주세요.")
else:
    print("F등급 입니다. 힘내주세요...")
```

<br>

## **논리 연산자 (and, or, not)**
논리 연산자는 bool 자료형을 위한 특별한 연산자다.    
논리 연산자는 복잡한 조건을 짧은 코드로 판단할 수 있는 도구이므로 잘 활용하도록 하자.

|연산자|의미|
|---|---|
|a **and** b|a, b 둘 다 True라면 True|
|a **or** b|a, b 중 하나라도 True라면 True|
|**not** a|a가 False일 때 True|


#### **and 연산**

|A|B||and|
|---|---|---|---|
|False|False||False|
|True|False||False|
|False|True||False|
|True|True||True|

#### **or 연산**

|A|B||or|
|---|---|---|---|
|False|False||False|
|True|False||True|
|False|True||True|
|True|True||True|

#### **not 연산**

|A||not|
|---|---|---|---|
|False||True|
|True||False|



<br>

# **숙제**
숙제는 본인 코딩 폴더내 '9월' 폴더에 저장하고, 숙제 검사는 수업 시간에 맡으면 됩니다.

### **1번**   
다음 조건식은 참일까요? 거짓일까요?
파일의 이름은 'HW1_condition.py'이며, 코드 복사 후 각 줄 옆에 주석으로 답을 적어두면 됩니다.
``` python
HW1_calculator.py
7 > 3
'apple' != 'kiwi'
not (11 <= 22)
not (2 == 3)
1 >= 1 and 4 < 3
```

<br>

### **2번**   
아래 코드를 그대로 작성해보고 출력 결과를 예상해보세요.   
파일의 이름은 'HW2_ball_box.py'이며, 복사 붙여넣기는 금지합니다.
``` python
# HW2_ball_box.py
red = 7
blue = 3

if red < blue:
    print("빨간색 공 2개를 꺼냅니다.")
    red = red - 2
else:
    print("빨간색 공 4개를 꺼냅니다.")
    red = red - 4

if red == blue:
    print("파란 공 3개를 꺼냅니다.")
    blue = blue - 3
else:
    print("빨간 공 3개를 꺼냅니다.")
    red = red - 3

if red > blue:
    print("빨간 공이 더 많이 있습니다.")
elif red < blue:
    print("파란 공이 더 많이 있습니다.")
else:
    print("빨간 공과 파란 공의 갯수가 같습니다.")
```

<br>

### **숙제 3번**   
아래 코드의 if문을 elif를 사용하도록 고쳐보세요.   
파일 이름은 'HW3_calculator.py'이며, 이 문제는 코드를 복사/붙여넣기 후 풀어도 좋습니다.
``` python
# HW3_calculator.py
num1 = 8
num2 = 2

op = input("+, -, *, / 중 하나를 입력하세요: ")

if op == "+":
    print("8 + 2 ", num1 + num2)
else:
    if op == "-":
        print("8 - 2 =", num1 - num2)
    else:
        if op == "*":
            print("8 * 2 =", num1 * num2)
        else:
            if op == "/":
                print("8 / 2 =", num1 / num2)
            else:
                print("잘못된 입력입니다.")
```

<br>

### **숙제 4번**   
아래 코드를 그대로 따라 작성하면 됩니다. 프로그램을 실행해보고 코드의 의미를 고민해보세요. 자세한 내용은 수업시간에 계속 됩니다~   
파일의 이름은 'HW4_guess_num.py'이며, 복사 붙여넣기는 금지합니다.
```python
# HW4_guess_num.py
target = 3
guess = input("맞출 숫자를 입력하세요: ")
guess = int(guess)

if guess < 1 or guess > 8:
    print("1~8 까지만 입력하세요")
else:
    if target == guess:
        print("숫자를 맞추셨어요 축하합니다!")
    elif guess > target:
        print("target보다 크다")
    else:
        print("target보다 작다")
```
