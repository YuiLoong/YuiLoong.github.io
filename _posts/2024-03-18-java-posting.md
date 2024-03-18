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
**3. var와 let과의 차이, let과 const와의 차이를 간략하게 설명하시오.**
<br>
<br>
<br>
  ✔️ 이건 예전 포스팅에서 언급한 적이 있으므로 [let과 const 차이] < 참고하면 된다.
<br>
  
[let과 const 차이]:https://yuiloong.github.io/java/2024-03-13-java-posting/#%EB%AC
