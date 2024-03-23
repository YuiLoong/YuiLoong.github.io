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
**5.사용자가 프롬프트 창에 숫자를 입력했을 때 그 숫자를 함수로 넘겨주고,** <br> 
**함수에서는 숫자가 양수인지, 음수인지, 또는 0인지 판단해서 알림 창에 보여주는 프로그램을 작성하시오.**
<br>
<br>
<br>
  ✔️ <br>
  
```js
function Whatint(n){
  if (n > 0) {
    alert(`${n}은 양수입니다.`);
  } else if (n < 0) {
    alert(`${n}은 음수입니다.`);
  } else {
    alert(`${n}은 0입니다.`);
  }
}

const number = parseInt(prompt("숫자를 입력하세요"));

if(!isNaN(number)){
  Whatint(number);
}

```
<br>
![첨부4](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0319_4.PNG?raw=true)
<br>
<br>

## 문제6 && 문제 풀이6
___
**6. 2개의 숫자를 입력받아 두 수의 최대공약수를 구하는 함수를 작성하고 테스트해 보시오.** <br>
**예를 들어 4와 12의 최대공약수는 4이다. 즉, 두 수 모두 나누어 떨어지는 수 중에서 가장 큰 값이 최대 공약수이다.**
<br>
>힌트: <br>
>1) 주어진 두 수 중에서 어떤 수가 큰 수인지 확인한다.<br>
>2) 두 수가 모두 나누어 떨어져야 하므로 두 수 중에서 큰 수까지 반복하면서 작은 수도 나누어 떨어지고, 큰 수도 나누어 떨어지는 수를 찾는다.<br>
>3) 찾을 때마다 변수에 할당한다. 반복이 모두 끝나면 변수에는 가장 마지막에 할당한 약수만 남는다.<br>

<br>
<br>

  ✔️ <br>

```js
function quiz2(num1,num2){
  if(num1 > num2){
    max = num1;
  }else{
    max = num2;
  }

  for(let i=1;i<=max;i++){
    if(num1%i==0 && num2%i==0){
        result = i
    }
  }
  return result;
}


let num1 = prompt("첫번째 숫자를 입력하세요");
let num2 = prompt("두번째 숫자를 입력하세요");
let result = 0;
alert(`${num1}과 ${num2}의 최대공약수 : ${quiz2(num1, num2)}`);

```
<br>

![첨부5](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0319_5.PNG?raw=true)
<br>
<br>
