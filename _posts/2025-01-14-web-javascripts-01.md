---
title: "[JavaScripts] 기초 문법"
excerpt: "기초 및 변수"

categories:
  - javascripts
tags:
  - [React, Web, JavaScript, 프론트엔드]

permalink: /web/javascripts01/

toc: true
toc_sticky: true

date: 2025-01-14
last_modified_at: 2025-01-14
---

# 제 2장 : 자바스크립트 기초 문법

## 자바스크립트 기초 문법

### 자바스크립트 선언문

```js
<script>자바스크립트 코드</script>

실제 사용법
<script>
  document.write("안녕하세요");
</script>
```

script 태그의 위치는 상관이 없다. <br>
head, body 둘 다 가능하다. <br>

### 자바스크립트 주석 방법

```js
// 한 줄 주석
/* 여러 줄 주석 */

<!-- HTML 주석 -->
```

JS 상에서 주석 방식과 html 상 주석 방식이 다르니 구분에 주의해야한다.

### 내부 스크립트 외부로 분리

```js
<script src="JS 파일 경로"></script>
```

가독성과 유지 보수를 위해 분리해서 작성하는 것이 좋다.

## 변수란?

<b>var</b> : 블록 밖과 안 선언 차이가 없음 <br>
<b>let</b> : 블록 안에서 사용하면 안에서만 사용 가능하다.

```js
// 사용 방법
var 변수명; 또는 var 변수명 = 값;
```

변수에 저장할 수 있는 자료형은 <b>문자형(string), 숫자형(num), 논리형(boolean), 빈 데이터(Undefined)</b>이 있다.

<h3>typeof</h3>
지정한 데이터 또는 변수의 자료형에 대해 알고 싶을 때 사용합니다. 기본형은 다음과 같다.

```js
  typeof 변수 또는 데이터
  //사용법
  var num = 100;
  var str = "자바스크립트";
  document.write(typeof num, "<br>");
  document.write(typeof str);
```
