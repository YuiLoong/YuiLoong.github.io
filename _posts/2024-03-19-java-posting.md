---
categories: Java
toc: true
---

## 자바스크립트 함수와 스코프 연습문제(1)
  <br> 
  <br>
  <br>
  <br>
 

## 문제1 && 문제 풀이1
___
**1.두 수를 받아서 곱하고 결괏값을 반환하는 함수를 만든 후 10과 20을 곱한 결괏값을 콘솔 창에 표시하는 코드를 작성하시오.** 
<br>
<br>
<br>
✔️
```js
function calc(a,b){
  let result = a*b;
  console.log(`두 수의 곱: ${result}`);
}
calc(10,20);
```
<br>
![첨부1](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0319_1.PNG?raw=true)
<br>
<br>

## 문제2 && 문제 풀이2
___
**2.화살표 함수를 사용해 두 수를 받아서 곱하는 함수를 정의한 후, 10과 20을 곱한 결괏값을 콘솔 창에 표시하시오.**
<br>
<br>
<br>

  ✔️ 
  <br>
  
```js
let mul = (a,b) => a*b;
console.log(`10*20 = ${mul(10,20)}`);
```
<br>
![첨부2](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0319_2.PNG?raw=true)
<br>
<br>

## 문제3 && 문제 풀이3
___
**3.콜백 함수를 이용해 사용자 이름과 나이를 입력하면 알림 창에 '안녕하세요? OOO님, 나이가 OO이군요.'라고 출력하는 코드를 작성하시오** <br>
<br>
<br>
  ✔️ <br>
  
  ```js
  function showData(name, age){
  alert(`안녕하세요 ${name}님, 나이가 ${age}세시군요.` )
}
function getData(callback){
  let userName = prompt("이름 입력하세요");
  let userAge = prompt("나이를 입력하세요");

  callback(userName,userAge);
}
getData(showData);
```
<br>
![첨부3](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0319_3.PNG?raw=true)
<br>
<br>
  
## 문제4 && 문제 풀이4
___
**4.다음 소스 코드를 실행하면 콘솔 창에 어떤 내용이 표시될 지 예상해 보시오.** <br>

```js
const user = {"His", "name", "is", "Hong"};
console.log(user);
console.log(...user);
```
<br>
<br>
✔️ 
<br>

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
