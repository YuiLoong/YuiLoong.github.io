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
✔️ 
<br>


| 입력값               | 결과값         | 해설
|:---------------------|:---------------|:---------------------------------------
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

## 문제8 && 문제 풀이8
___

**​사용자로부터 숫자 2개를 입력받아 첫 번째 입력받은 숫자가 큰 지, 두 번째 입력받은 숫자가 큰지를**<br>
**구하는 프로그램을 작성하시오.** <br>

<br>
<br>
  ✔️ <br>
  
  ```js
  const one = prompt("첫번째 숫자를 입력하세요");
  const two = prompt("두번째 숫자를 입력하세요");

  if(one > two){
    console.log("첫번째 숫자가 더 큽니다.");
  }else if(one < two){
    console.log("두번째 숫자가 더 큽니다.");
  }else{
    console.log("둘다 같습니다.");
  }
  ```
<br>
<br>

## 문제9 && 문제 풀이9
___

**​​9.사용자로부터 숫자를 입력받아 양수, 0, 음수를 구분하는 프로그램을 작성하시오.** <br>

<br>
<br>

  ✔️ <br>
  
  ```js
  const n = prompt("숫자를 입력하세요");

  if(n>0){
    console.log("양수입니다.");
  }else if(n<0){
    console.log("음수입니다.");
  }else if(n==0){
    console.log("0입니다.");
  }
  ```
<br>
<br>

## 문제10 && 문제 풀이10
___

**10. 사용자로부터 월을 입력받아 무슨 계절인지 출력하는 프로그램을 작성하시오.** <br>

<br>
<br>

  ✔️ <br>
  
  ```js
  const n = prompt("월(달)를 입력하세요");

  if(n==12 || n==1 || n==2){
    console.log(`${n}월은 겨울`);
  }else if(n==3 || n==4 || n==5){
    console.log(`${n}월은 봄`);
  }else if(n==6 || n==7 || n==8){
    console.log(`${n}월은 여름`);
  }else if(n==9 || n==10 || n==11){
    console.log(`${n}월은 가을`);
  }
  ```
<br>
<br>

## 문제11 && 문제 풀이11
___

**11. 다음 프로그램에서 같은 결과가 나오도록  for of 문을 for in  문으로 바꾸시오.** <br>

```js
let array = [52, 273, 32, 93, 103];

for (let element of array) {
    console.log(element);
}
```
<br>

<br>
<br>

  ✔️ <br>
  
  ```js
let array = [52, 273, 32, 93, 103];

for (let element in array) {
    console.log(array[element]);
}
```
<br>
<br>

## 문제12 && 문제 풀이12
___

**12. 1부터 100까지 숫자를 곱하는 프로그램을 작성하시오.** <br>

<br>
<br>

  ✔️ <br>
  
  ```js
  let sum = 1;

  for(let i=1;i<=100;i++){
      sum = sum*i;
  }
  console.log(s);
  ```
<br>
<br>
## 문제12 && 문제 풀이13
___

**13. 숫자 1부터 999까지 짝수가 몇 개인지 출력하는 프로그램을 작성하시오.** <br>

<br>
<br>

  ✔️ <br>
  
  ```js
  let cnt = 0;

  for(let i=1;i<=999;i++){
      cnt++;
  }
  console.log(cnt);
  ```
<br>
<br>
