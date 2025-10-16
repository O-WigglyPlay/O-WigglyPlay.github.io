---
title: '[JavaScript] 기초 문법'
excerpt: '조건문과 선택문'

categories:
    - JavaScript
tags:
    - [React, Web, JavaScript, 프론트엔드]

permalink: /web/javascript03/

toc: true
toc_sticky: true

date: 2025-01-16
last_modified_at: 2025-01-16
---

# 제3장 : 제어문

**제어문**은 프로그램의 흐름을 제어하는 문장으로 조건문과 반복문으로 구성되어있다.

## 조건문

`조건문`은 조건식의 참 거짓에 따라 자바스크립트 코드를 제어한다. <br>

### if문

`if` 문은 가장 기본적인 조건문입니다.

```javascript
//기본형
if (조건식) {
    //조건식이 참이면 코드 실행
}
//실적용법
var num = 10;
if (num < 500) {
    //num이 500보다 작으면 조건문 내 코드를 실행한다.
    document.write('hello');
}
```

**조건식에 논리형 데이터가 아닌 다른 형이 오는 경우** <br>
다음 조건 식이 오는 경우 false를 반환하며 그 밖의 값은 true를 반환한다.

```md
0, null, ""(빈 문자), undefined
```

### else문

else문은 조건식을 만족하는 경우와 만족하지 않는 경우를 따질 때 사용합니다.

```javascript
//기본형
if(조건식)
    자바스크립트 코드1;
} else {
    자바스크립트 코드2;
}

//적용예제
var num = 10;
if(num < 500) { //num이 500보다 작으면 조건문 내 코드를 실행한다.
    document.write("hello");
} else{ //조건에 맞지 않을 시 출력한다.
    document.write("더 많은 수가 필요합니다.");
}
```

### else-if문

else if문은 두 가지 이상의 조건식과 정해 놓은 조건을 만족하지 않았을때 실행되는 코드입니다.

```javascript
if(조건식1){
    자바스크립트 코드1;
} else if(조건식 2){
    자바스크립트 코드2;
} else if(조건식 3){
    자바스크립트 코드3;
} else{
    자바스크립트 코드4;
}
```

## 선택문

### switch문

if문과 비슷한 용도로 사용되는나 if문은 여러 값을 비교하기 위해 사용하며 switch문은 여러 값 중 일치하는 데이터를 찾아서 그에 해당하는 코드를 실행시킬때 사용한다.

```javascript
var 변수 = 초기값;
switch (변수) {
    case 값1:
        코드1;
        break;
    case 값2:
        코드2;
        break;
    case 값3:
        코드3;
        break;

    default:
        코드4;
}
```

변수에 저장된 값이 switch문을 지날때 case의 값을 하나씩 검사하며 지나가게 됩니다. <br>
이 후 일치하는 데이터가 있으면 그에 해당하는 코드를 실행하고 break문을 통해 switch문을 종료하게 됩니다. <br>
만약 일치하는 값이 없다면 default 값을 실행하며 종료하게 됩니다.
