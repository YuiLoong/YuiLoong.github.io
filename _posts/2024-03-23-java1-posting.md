---
categories: Java
toc: true
---

## 자바스크립트 함수와 스코프 연습문제(2)
  <br> 
  <br>
  <br>
  <br>
 

## 문제1 && 문제 풀이1
___
**1.다음 중 코드에서 사용한 함수 정의 방법을 모두 고르세요.** 
<br>

```js
const add = function(){};
```
<br>
① 함수 표현식
<br>
② 함수 선언문
<br>
③ 화살표 함수
<br>
④ 네이밍 함수
<br>
⑤ 익명 함수
<br>
<br>
<br>
✔️

<br>
<span style="color: red;">① 함수 표현식</span>
<br>
❖ 변수로 저장할 수 있으며, 이 변수는 함수처럼 사용 가능해진다.
<br>
<br>

② 함수 선언문
<br>
❖ `function`으로 시작한다.
<br>
<br>

③ 화살표 함수 
<br>
❖ (매개변수) => {함수 내용}
<br>
<br>

④ 네이밍 함수
<br>

<span style="color: red;">⑤ 익명 함수</span>
<br>
❖ var 변수명 = function(매개변수){실행문;};
<br>
<br>

## 문제2 && 문제 풀이2
___
**2.코드에서 max 변수의 출력값이 배열 중 가장 큰 숫자가 될 수 있도록 getArrayNumber() 함수를 완성하세요.** <br>
**이때, 배열 요소는 반드시 숫자형이라고 가정합니다.**
<br>
```js
function getArrayMaxNumber(arr){ 
    /* 함수 코드를 완성하세요 */ 
}
const max = getArrayMaxNumber([10, 50, 30]);
console.log(max); 
```
<br>
<br>
<br>

  ✔️ 
  <br>
  
```js
function getArrayMaxNumber(arr){ 
    let max = arr[0]; 
    for(let i=0;i<arr.length;i++){
        if(arr[i]>max){
            max = arr[i];
        }
    }
    return max;
}
const max = getArrayMaxNumber([10, 50, 30]);
console.log(max);
```
<br>
<br>
<br>

## 문제3 && 문제 풀이3
___
**3.다음 중 코드를 실행했을 때 콘솔창에 출력될 값을 고르세요.** <br>
```js
var text = "outside";
function printScope(){
  console.log(text);
  var text = "inside";
};
printScope();
```
<br>
① outside
<br>
② inside
<br>
③ null
<br>
④ undefined
<br>
⑤ " "
<br>
<br>
<br>

  ✔️ <br>
  
① outside
<br>
② inside
<br>
③ null
<br>
<span style="color: red;">④ undefined</span>
<br>
❖ 아직 값이 할당되기 전에 출력되므로 ``undefined`가 출력된다.
<br>
<br>
⑤ " "
<br>
<br>
<br>
  
## 문제4 && 문제 풀이4
___
**4. 다음 코드를 실행하면 출력될 변수 result의 값을 고르세요.** <br>

```js
const result = (function(a, b){
  function init(){
    return doSum(a, b);
  }
  function doSum(a, b){
    return a + b;
  }
  return init();
})(10, 20);
console.log(result);
```
<br>
① undefined
<br>
② null
<br>
③ 50
<br>
④ 30
<br>
⑤ SyntaxError
<br>
<br>
✔️ 
<br>
① undefined
<br>
② null
<br>
③ 50
<br>
<span style="color: red;">④ 30</span>
<br>
❖ a=10, b=20 값이 들어가서 dosum()함수 실행.
<br>
<br>
⑤ SyntaxError
<br>
<br>

## 문제5 && 문제 풀이5
___
**5. 원의 넓이를 구하는 공식은 (반지름) × (반지름) × (원주율)입니다.** <br>
**원주율은 3.14라고 했을 때, 원의 반지름을 이용해 원의 넓이를 반환하는 함수를 만들어 보세요.**
<br>
*(콘솔 출력) 반지름 ○인 원의 넓이는 □ □ □입니다.)*
<br>
<br>
<br>
  ✔️ <br>
  
```js
function Circle(radius) {
    const pi = 3.14;
    const s = pi * radius * radius;
    return s;
}

const radius = prompt("반지름 입력하세요"); // 반지름
const s = Circle(radius); // 함수 호출을 통해 원의 넓이 계산
console.log(`반지름 ${radius}인 원의 넓이는 ${s}입니다.`);

```
<br>

![첨부1](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0323_1.png?raw=true)
<br>
<br>

## 문제6 && 문제 풀이6
___
**6. 매개변수로 배열을 전달받아 배열의 요소 중에서 가장 큰 수를 찾아 반환하는 함수를 만들어 보세요.** <br>
**이때, 배열 안의 데이터는 모두 0보다 큰 정수라고 가정합니다.** <br>
>*테스트 배열: [10, 20, 50, 5, 30]* <br>
>*콘솔 출력) 가장 큰 수는 50입니다.*
<br>
<br>
<br>

  ✔️ <br>

```js
function Number(arr) {
    let max = arr[0]; 
    
    for (let i = 0; i < arr.length; i++) {
        if (arr[i] > max) {
            max = arr[i]; 
        }
    }
    return max; // 최대값 반환
}

const testArray = [10, 20, 50, 5, 30];
const MaxNumber = Number(testArray);
console.log(`가장 큰 수는 ${MaxNumber}입니다.`);

```
<br>

![첨부5](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0323_2.png?raw=true)
<br>
<br>

## 문제7 && 문제 풀이7
___
**7.체질량 지수(BMI)를 계산하는 공식은 몸무게를 키(m)의 제곱으로 나눈 값입니다.** <br>
**사용자에게 키(cm)와 몸무게(kg)에 해당하는 값을 전달받아 체질량 지수를 계산합니다.** <br>
**체질량 지수가 26점 이상이면 비만, 24-25점은 과체중, 18.5-23점은 정상, 18.5점 미만은 저체중을 반환하는 함수를 만들어 보세요.**
<br>
>테스트 #1) 키: 180cm, 몸무게: 100kg → 콘솔출력: 비만 <br>
>테스트 #2) 키: 180cm, 몸무게:   80kg → 콘솔출력: 과체중 <br>
>테스트 #3) 키: 180cm, 몸무게:   70kg →콘솔 출력: 정상 <br>
>테스트 #4) 키: 180cm, 몸무게:   59kg → 콘솔출력: 저체중 <br>

<br>
<br>

  ✔️ <br>

```js
function BMI(height, weight) {
    const heightMeter = height / 100; // cm -> m으로 변환
    const bmi = weight / (heightMeter * heightMeter); // bmi 공식

    if (bmi >= 26) {
        return "비만";
    } else if (bmi >= 24 && bmi <= 25) {
        return "과체중";
    } else if (bmi >= 18.5 && bmi <= 23) {
        return "정상";
    } else {
        return "저체중";
    }
}

// 입력 받고 값 출력
let height = prompt("키 입력하세요");
let weight = prompt("몸무게 입력하세요");
console.log(`키: ${height}cm, 몸무게: ${height}kg 은 ${BMI(height, weight)}`);

```
<br>

![첨부5](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0323_3.png?raw=true)
<br>
<br>
