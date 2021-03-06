---
title: Java Data Type
date: 2018-06-14 21:27:36
categories:
  - JAVA
tags:
    - java
    - oop
    - 객체지향
    - 데이터타입
    - byte
    - 숫자
    - 정수
    - 실수
    - 문자
    - 문자열
    - long
    - float
    - 암시적형변화
    - 명시적형변화
thumbnail: https://tuhbm.github.io/images/bnr-java.jpg
---
## JAVA
이 카테고리는 자바를 공부 하며, 익힌 내용을 기록합니다.
책을 보며, 또는 독학을 하므로 `잘못된 내용이 있으면 댓글 또는 메일주시면 신속히 오류처리하겠습니다.`
*****

# 데이터 타입
![data](https://tuhbm.github.io/images/java/img_data.jpg)
프로그래밍에서 데이터는 데이터형식, 메모리의 소비크기, 표현가능범위에 따라 알맞게 사용해야합니다.
그 내용은 데이터의 형식을 알아보면서 알아보겠습니다.
<!-- more -->
## 숫자

### 정수형

|데이터 타입  | 메모리의 크기 |  표현 가능 범위|
|----------|-----------|---------------|
|byte | 1 byte | -128 ~ 127|
|short | 2 byte | -32,768 ~ 32,767|
|int | 4 byte | -2,147,483,648~2,147,483,647|
|long | 8 byte | -9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807|


### 실수형

|데이터 타입 | 메모리의 크기 | 표현 가능 범위|
|----------|-----------|---------------|
|float | 4byte | ±(1.40129846432481707e-45 ~ 3.40282346638528860e+38)|
|double | 8byte | ±(4.94065645841246544e-324d ~ 1.79769313486231570e+308d)|

여기서 문제를 내보겠습니다.
````
long a = 123123123;
long b = 123;
````
_이 변수의 메모리의 크기는 같을까요? 다를까요?_

정답은 같습니다.

하지만 a에는 123132123이라는 큰 숫자가 들어갔지만,
b에는 123이라는 작은 숫자가 들어갔습니다. 그럼에도 불구하고 메모리의 크기는 같습니다.
`컴퓨터 프로그래밍은 결국 메모리를 어떻게 사용하느냐`에 따라 성능의 차이가 나타납니다.
위의 b와같은 경우처럼 작은 숫자를 이용할때는 byte를 사용해야 하는것처럼 `알맞은 데이터형태를 선언`하므로써 **메모리의 용량**을 아낄수 있습니다.
**추가적으로 오늘날 하드웨어의 발달로 인해 메모리의 용량이 많이 향상되어, 정수를 사용할때는 충분히 편하게 큰 수를 표현 할 수 있는 데이터 타입인 int를 주로 사용합니다.**

### 명시적 데이터타입

명시적으로 데이터 형태를 표기해줘야 하는 데이터타입 형태가 있다.
````
int a = 2.2;
````
에러가 납니다. 2.2는 실수형 타입입니다. 그렇다면 실수형 타입인 float으로 변경해보겠습니다.
````
float a = 2.2;
````
에러가 납니다.
그렇다면 double형태를 사용해보겠습니다.
````
double a = 2.2;
````
에러가 나지않습니다.
이는 2.2는 double형태의 데이터값이라는 것입니다.
'float의 데이터형태는 언제 사용하지...?'라는 의문이 듭니다.
`float`의 데이터 타입은 명시적으로 값에 float의 형태의 값이라는 `F`을 지정해줘야합니다.
````
float a = 2.2F;
````
이렇게 하니 에러가 안나는 것을 확인 할 수 있습니다.
````
int a = 2147483648;
````
int는 2,147,483,647까지 밖에 표현을 못합니다.
그러면 큰값을 표기할 수 있는 long의 데이터 형태를 사용해보겠습니다.
````
long a = 2147483648;
````
에러가 납니다. 이부분 역시 float의 형태와 같이 명시적으로 값을 지정해주겠습니다.
````
long a = 2147483648L;
````
이렇게 명시적으로 값을 `long`의 데이터 타입 `L`을 지정해주니 에러가 발생하지 않습니다.

byte나 short의 데이터의 형태같은경우 자바에서 자체적으로 편하게 사용하기위해 int의 데이터값을 허용하고 있습니다. 단 허용범위내에 표시 할 수 있는 경우에 한에서만 가능합니다.

이부분은 [생활코딩 강좌](https://opentutorials.org/course/1223/5326)를 참고하였습니다.

*****
## 문자

|데이터 타입 | 메모리의 크기 | 표현 가능 범위|
|----------|-----------|---------------|
|char | 2byte | 모든 유니코드 문자|

자바에서는 문자와 문자열이 다릅니다. 
**문자(character)는 글자 하나를 의미하고, 문자열은 글자들의 집합**을 의미합니다.

### 문자열
|데이터 타입 | 메모리의 크기 | 표현 가능 범위|
|----------|-----------|---------------|
|String | 글자당 2byte | 모든 유니코드 문자|

## 자동 형 변환
서로 다른 데이터 타입의 형태의 숫자가 있다고 이를 더해야 한다고 생각을 해봅시다.
예를들면 int와 byte값이 있다면 이는 데이터형태가 다르므로 더하기가 안되야합니다.
````
int a = 20;
byte b = 10;
int p = a+b;
System.out.println(p); //30
````
실행이 되는 것을 볼 수 있습니다.

'자바는 형태에 따른 오류를 방지하기 위한 엄격한 언어인데..'라는 생각이 들겠지만,
자바도 유연함을 갖추고 있습니다.
바로 표현 할 수 있는 메모리의 크기별로 데이터의 손실이 발생하지 않으므로,
`자동으로 형변환`을 합니다.

또한 실수는 정수를 포함하지만, 정수는 실수를 포함 할 수 없습니다.
이처럼 데이터 형태에 따라 자동으로 형변환이 가능한부분을 표기해보면
`byte => short, char => int => long => float => double`
순서로 **자동으로 형변환**이 됩니다.

## 명시적 형 변환
자동으로 형변환이 되지 않는 부분들은 직접 `명시적 형 변환`을 해야 합니다.
````
int a = 100.0F;
````
이러한 변수타입은 에러가 발생합니다.
데이터형태는 int형태이나 값은 float의 형태이기 때문입니다.
이와같은경우 명시적 형 변환이 필요합니다.
````
int a = (int) 100.0F;
````
이렇게 값앞에 (int)을 적어주므로써 값을 명시적으로 int의 데이터형태로 변화하였습니다.

다른 예를 들어보겠습니다.
````
int b = 100.1F;
````
변환해보겠습니다.
````
int b = (int) 100.1F;
````
결과는 100이 출력됩니다.
int의 형태로 변경하기위해 소수점이하를 버림으로 처리하기 때문입니다.
이와 같은경우 기존에 갖고 있던 `데이터의 손실이 발생`합니다. 데이터의 손실이 발생하지않도록 곱하기를 하거나 더하기와 같이 추가적인 계산을 통해 데이터 손실이 발생하지 않도록 해야 합니다.

이번 포스팅을 통해 `데이터의 타입과 형변환`에 대해 알아보았습니다.
다음시간엔 `비교연산자와 배열`에 대해 알아보도록하겠습니다.
