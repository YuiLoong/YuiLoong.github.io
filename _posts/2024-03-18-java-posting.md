---
categories: Java
toc: true
---

## 자바스크립트 연산자와 제어 문제(1)
  <br> 
  <br>
  <br>
  <br>
 

## 문제1 && 문제 풀이1
___
**1. 다음 프로그램의 실행 결과를 예측해 보시오.** <br>
```js
console.log(2 + 2 - 2 * 2 / 2 * 2);
console.log(2 - 2 + 2 / 2 * 2 + 2);
```
<br>
<br>
<br>
✔️<span style="color: red;"> 0 <br> 4 </span>
<br>
첫번째줄 순서) `/` -> `*` -> `*` -> `+` , `-` = 0 <br>
두번째줄 순서) `/` -> `*` -> `-` , `+` = 4 <br>
<br>

## 문제2 && 문제 풀이2
___
**2. 다음 코드의 실행 결과를 적으시오.**
<br>
```js
  const number = 10;

  console.log(number++);
  console.log(++number);
  ```
<br>
<br>
<br>

  ✔️ 
 <span style="color: red;"> 에러 결과가 나온다. </span><br>
`let`으로 number를 선언한다면 "11"이 나온다.
<br>
<br>

## 문제3 && 문제 풀이3
___
**3. 다음의 표현식이 false와 true로 나오는 이유를 설명하시오.** <br>
```js
"A" > "B"                        // false
"Javascript" > "JAVASCRIPT"      // true
```
<br>
<br>
<br>
  ✔️ <span style="color: red;">아스키코드 값 때문에 </span>
<br>
<br>
  
## 문제4 && 문제 풀이4
___
**4. 다음 코드의 주석 부분에 변수 x, y의 값을 표에 있는 값과 같이 할당할 때** <br>
**나오는 출력 결과를 쓰시오.** <br>
```js
let x, y;
// 값 할당 부분

if (x > 4) {
    if (y > 2) {
        console.log(x * y);
    }
} else {
    console.log();
}
```
<br>
✔️ <br>


| 입력값               | 결과값         | 해설
|:---------------------|:---------------|:-------------------------------------------
| x = 2, y = 10        |                | x 값이 조건에 안 맞음
| x = 1, y = 4         |                | x 값이 조건에 안 맞음
| x = 10, y = 2        |                | y 값이 조건에 안 맞음 
<br>
<br>

## 문제5 && 문제 풀이5
___
**5. 다음의 중첩 조건문을 논리 연산자를 사용해 하나의 if 조건문으로 작성하시오.**
<br>
```js
if (x > 10) {
    if (y > 20) {
        console.log("조건에 맞습니다.");
    }
}
```
<br>
<br>
<br>
  ✔️ <br>
  
```js
if( x > 10 && y > 20) console.log("조건에 맞습니다.");
```
<br>
<br>

## 문제6 && 문제 풀이6
___
**6. 다음과 같이 if 문으로 작성된 코드를 swith 문으로 바꾸시오.**
<br>
```js
// 학년 변수를 생성한다.
let level = 1;

// 출력한다.
if (level == 1) {
    console.log("수강해야 하는 전공 학점: 12학점");
} else if (level == 2) {
    console.log("수강해야 하는 전공 학점: 18학점");
} else if (level == 3) {
    console.log("수강해야 하는 전공 학점: 10학점");
} else if (level == 4) {
    console.log("수강해야 하는 전공 학점: 18학점");
}
```
<br>
<br>
<br>
  ✔️ <br>

```js
// 학년 변수를 생성한다.
let level = 1;

// 출력한다.
switch (level) {
  case 1:
    console.log("수강해야 하는 전공 학점: 12학점");
  case 2: 
    console.log("수강해야 하는 전공 학점: 18학점");
  case 3:
    console.log("수강해야 하는 전공 학점: 10학점");
  case 4:
    console.log("수강해야 하는 전공 학점: 18학점");
}
```
<br>
<br>
## 문제7 && 문제 풀이7
___

**​7. 다음 프로그램의 실행 결과를 예측해 보시오.** <br>
```js
const array = ['사과', '배', '귤', '바나나'];

console.log('# for in 반복문');
for (const i in array) {
    console.log(i);
}

console.log('# for of 반복문');
for (const i of array) {
    console.log(i);
}
```
<br>
<br>
<br>
  ✔️ <br>
  
  <span style="color: red;"> in 반복문은 `0 1 2 3`, of 반복문 `사과 배 귤 바나나` </span>
<br>
<br>
