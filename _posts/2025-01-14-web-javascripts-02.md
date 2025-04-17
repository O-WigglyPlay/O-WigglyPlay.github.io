---
title: "[JavaScripts] 기초 문법"
excerpt: "연산자"

categories:
  - javascripts
tags:
  - [React, Web, JavaScript, 프론트엔드]

permalink: /web/javascripts02/

toc: true
toc_sticky: true

date: 2025-01-14
last_modified_at: 2025-01-14
---

연산자에는 다양한 종류가 있다.

## 연산자란 ?

산술, 문자 결합, 대입, 증감, 비교, 논리, 삼항 조건 연산자가 있다. <br>
예를 들어 자신의 평균 체중을 구할 때 빼고 곱하는 작업 등은 산술 연산자를 이용한다. 그리고 이렇게 빼기, 더하기, 곱하기, 나누기 등을 하는 일련의 작업을 연산 작업이라 한다.

### 산술 연산자

산술 연산자는 더하기,빼기, 곱하기, 나누기, 나머지가 있다.

| 종류 | 기본형 |  설명  |
| :--: | :----: | :----: |
|  +   |  A+B   | 더하기 |
|  -   |  A-B   |  빼기  |
|  \*  |  A\*B  | 곱하기 |
|  /   |  A/B   | 나누기 |
|  %   |  A%B   | 나머지 |

```js
<script>
  var num1 = 15;
  var num2 = 2;
  var result;
  result = num1 + num2;
  document.write(result, "<br>"); //17
  result = num1 - num2;
  document.write(result, "<br>"); //13
  result = num1 * num2;
  document.write(result, "<br>"); //30
  result = num1 / num2;
  document.write(result, "<br>"); //7.5
  result = num1 % num2;
  document.write(result, "<br>"); //1
</script>
```

### 문자 결합 연산자

여러개의 문자를 하나의 문자형 데이터로 결합할 때 사용한다. <br>
문자형과 다른 피연산자와 더하면 데이터는 자동으로 문자형 데이터로 형 변환이 된다.

```
Ex) "java" + "script" = "javascript";
EX) "100" + 50 = "10050";
```

```js
<script>
  var t1 = "학교종이"; var t2 = " 땡땡땡 "; var t3 = 8282; var t4 = " 어서
  모이자 "; var result; result = t1 + t2 + t3 + t4; document.write(result);
  //학교종이 땡땡땡 8282 어서 모이자
</script>
```

### 대입 연산자

대입 연산자는 연산된 데이터를 변수에 저장할때 사용한다.
복합 대입 연산자는 산술 연산자와 대입 연산자가 복합적으로 적용된 것이다.

|  종류   |   풀이   |
| :-----: | :------: |
|  A = B  |  A = B   |
| A += B  | A = A+B  |
| A -= B  | A = A-B  |
| A \*= B | A = A\*B |
| A /= B  | A = A/B  |
| A %= B  | A = A%B  |

```js
<script>
  var num1 = 10;
  var num2 = 3;

  num1 += num2;
  document.write(num1, "<br>"); //13
  num1 -= num2; //num1 = 13;
  document.write(num1, "<br>"); //10
  num1 *= num2; //num1 = 10;
  document.write(num1, "<br>"); //30
  num %= num2;  //num1 = 30;
  document.write(num1, "<br>"); //0
</script>
```

### 증감 연산자

증감 연산자는 숫자형 데이터를 1씩 증가시키는 연산자와 1씩 감소시키는 연산자를 뜻한다.

```js
<script>
  var num1 = 10;
  var num2 = 20;
  var result;

  num1--; //9
  document.write(num1, "<br>");

  num1++; //10
  document.write(num1, "<br>");

  result = num2++;  //result: 20, num2: 21;
  document.write(result, "<br>");

  result = ++num2;  //result: 22, num2: 22;
  document.write(result, "<br>");
</script>
```

++의 위치에 따라 대입을 하고 계산할지 계산하고 대입할지가 달라진다.

### 비교 연산자

두 데이터의 값을 '크다, 작다, 같다'로 비교할 때 사용되는 연산자이다. 결과값은 참,거짓으로 표현된다.

| 종류  |          설명          |                        비고                         |
| :---: | :--------------------: | :-------------------------------------------------: |
|  A>B  |    A가 B보다 크다.     |                                                     |
|  A<B  |    A가 B보다 작다.     |                                                     |
| A>=B  | A가 B보다 크거나 같다. |                                                     |
| A<=B  | A가 B보다 작거나 같다. |                                                     |
| A==B  |     A와 B는 같다.      | 자료형과는 별개로 표기된 숫자만 같으면 true로 반환  |
| A!=B  |    A와 B는 다르다.     | 자료형과는 별개로 표기된 숫자만 같으면 false로 반환 |
| A===B |     A와 B는 같다.      |     표기된 숫자와 자료형이 같아야만 true로 반환     |
| A!==B |    A와 B는 다르다.     |    표기된 숫자와 자료형이 같아야만 false로 반환     |

### 논리 연산자

논리 연산자는 ||(OR), &&(AND), !(NOT) 으로 구성되어 있으며 true, false로 값을 반환한다.

| 종류 |                                               설명                                                |
| :--: | :-----------------------------------------------------------------------------------------------: |
| \|\| |     or 연산자라고 부르며, 피연산자 중 값이 하나라도 true가 존재하면 true로 결과값을 반환한다.     |
|  &&  |   and 연산자라고 부르며, 피연산자 중 값이 하나라도 false가 존재하면 false로 결과값을 반환한다.    |
|  !   | not 연산자라고 부르며 단항 연산자이다. 피연산자의 값이 true이면 반대로 false로 결과값을 반환한다. |

### 연산자 우선순위

```
1. ()
2. 단항 연산자(--,++,!)
3. 산술 연산자(*,/,%,+,-)
4. 비교 연산자(>,>=,<,<=,==,===,!==,!=)
5. 논리 연산자(&&,||)
6. 대입(복합 대입)연산자(=,+=,-=,*=,/=,%=)
```

### 삼항 조건 연산자

조건식의 결과에 따라 실행 결과가 달라지는 삼항 연산자로 피연산자가 3개 필요하다.<br>
if문과 비슷하며 조건식의 만족 여부에 따라 실행하는 코드를 다르게 하고자 할때 사용한다.

```
조건식 ? 자바스크립트 코드1 : 자바스크립트 코드2
```

```js
<script>
  var a = 10; var b = 3; var result = a > b ? "javascript" : "hello"; //a가
  b보다 큰가? 크다면 javascript를 작다면 hello를 출력해라
  document.write(result); //javascript
</script>
```
