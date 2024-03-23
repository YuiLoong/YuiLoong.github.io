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
**1. desc라는 id 선택자를 사용한 요소에 접근하는 코드를 작성해 보세요.** 
<br>
<br>
<br>
✔️
<br>

```js
document.querySelector("#desc")
```

<br>
<br>

## 문제2 && 문제 풀이2
___
**2. 05\index.html에서 '주소 : somewhere'에 접근하는 코드를 작성해 보세요.**
<br>
<br>
<br>

  ✔️ 
<br>
```js
document.querySelectorAll(".user")[1]
```
<br>
<br>
<br>

## 문제3 && 문제 풀이3
___
**3. 05\js-content-2.js를 수정해서 연락처를 클릭하면 '1234-5678'이 '1111-2222'로 바뀌게 하시오.** <br>
<br>
<br>

  ✔️ <br>

```js
const userName = document.querySelector("#desc p");
userName.onclick = () => userName.innerHTML = `연락처 : <b>1111-2222</b>`;
``` 
<br>
<br>
<br>
  
## 문제4 && 문제 풀이4
___
**4. 05\js-css.js를 수정해 '이름 도레미' 부분을 클릭하면 글자색이 red로 바뀌는 코드를 작성해 보세요.** <br>
<br>
<br>
✔️ 
<br>
```js
const userName = document.querySelector("#desc p");
userName.onclick = () => {
  userName.style.color = "red";
};
```
<br>
<br>

## 문제5 && 문제 풀이5
___
**5. style.css 파일에는 .blue-italic 스타일도 정의되어 있으므로 05\js\classlist-3.js 파일을 수정해** <br>
**'이름:도레미' 부분을 클릭할 때마다 이 스타일을 토글시키는 소스를 작성해 보세요.** <br>
<br>
<br>
  ✔️ <br>
  
```js
const title = document.querySelector("#title");
const userName = document.querySelector("#desc p");

title.onclick = () => {
  title.classList.toggle("clicked");  
}
userName.onclick = () => {
  userName.classList.toggle("blue-italic");
}
```
<br>
<br>

## 문제6 && 문제 풀이6
___
**6. 05\order.html 문서에서 '상품' 항목에 내용을 입력한 후** <br>
**자바스크립트를 사용해 입력한 내용을 가져오는 코드를 작성해 보세요.**
<br>
<br>
<br>

  ✔️ <br>

```js
document.querySelector("#product")
document.querySelector("#product").value
```
<br>
<br>

## 문제7 && 문제 풀이7
___
**7.05\login.html 문서에서 '아이디' 필드에 있는 값을 가져오는 소스를 작성해 보세요.**
<br>
<br>
<br>

  ✔️ <br>

```js
document.forms[0].elements[0]
```
<br>
<br>

## 문제8 && 문제 풀이8
___
**8.05\quiz-1.html 문서에는 [상세 설명 보기 / 닫기] 버튼이 있는데,** <br>
**이 버튼을 클릭할 때마다 상세 설명이 나타나거나 사라지도록 코드를 작성해 보시오.**
<br>

>상세 설명이 있는 영역을 가져와서 변수로 저장한다. <br>
>버튼을 가져와서 변수로 저장한다.<br>
>문서에는 .hidden {display: none; } 스타일이 만들어져 있다.<br>
>버튼을 클릭할 때마다 클래스 리스트의 toggle() 함수를 사용해 .hidden 스타일이 토글되도록 한다.<br>
<br>
<br>

  ✔️ <br>

```js
const viewBttn = document.querySelector("#view");
const detail = document.querySelector("#detail");

viewBttn.onclick = function() {
  detail.classList.toggle("hidden");
}
```
<br>
<br>

## 문제9 && 문제 풀이9
___
**9. 4장에서 작성한 '두 수의 최대공약수 구하기' 함수를 그대로 사용화면서 화면에 2개의 값을 입력한 후** <br>
**[계산하기] 버튼을 클릭했을 때 함수를 실행하고, 함수의 실행 결과는 '결과' 항목에 표시해 보시오** <br>
<br>
<br>
<br>

  ✔️ <br>

```js
const n = document.querySelector("#number1");
const m = document.querySelector("#number2");
const button = document.querySelector("button");
let result = document.querySelector("#result");

button.onclick = function() {
  result.innerText = getGCD(n.value, m.value);
}

function getGCD(n, m) {
  let max = n > m ? n : m;
  let GCD = 0;
  for (let i = 1; i <= max; i++) {
    if (n % i === 0 && m % i === 0) {
      GCD = i;   
    }
  }
  return GCD;
}


```
<br>
<br>

