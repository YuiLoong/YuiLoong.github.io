---
categories: Java
toc: true
---

## 자바스크립트 DOM 기초 문제(2)
  <br> 
  <br>
  <br>
  <br>
 

## 문제1 && 문제 풀이1
___
**1. 다음 코드에서 p 요소 노드를 선택하는 방법으로 올바르지 않은 것을 고르세요.** 
<br>

```js
<body>
    <div class="box1">
        <p id="text">Select Text</p>
    </div>
</body>
```
<br>
① document.getElementById("#text")
<br>
② document.querySelector("p")
<br>
③ document.querySelector(".box1 > p")
<br>
④ document.querySelectorAll("p")[0]
<br>
<br>
<br>
✔️
<br>
<span style="color: red;">① document.getElementById("#text")</span>
<br>
  ❖ `text`선택자를 기준으로 접근/ 이때 `#text`가 아닌 `text`으로 바꿔준다.
<br>
② document.querySelector("p")
<br>
③ document.querySelector(".box1 > p")
<br>
  ❖ box1 밑에 있는 자식(자손)으로 첫번째 요소가 도출
<br>
④ document.querySelectorAll("p")[0]
<br>
<br>

## 문제2 && 문제 풀이2
___
**2. 다음과 같은 코드에서 sample text를 클릭했을 때, p 태그의 fz20 클래스 속성을 삭제하고,** <br>
**sample text를 change text로 변경하고 싶다면 (가), (나)에 들어갈 내용으로 맞게 짝지어진 것을 고르세요.**
<br>

```js
   <p id="text" class="red-color fz20">sample text</p>
    <script>
        const pEl = document.querySelector("#text");
        pEl.onclick = () => {
            pEl.(가) = "change text"; 
            pEl.(나);
        }
    </script>
```
<br>

**(가) - (나)**
<br>
① dataset - removeClass("fz20")
<br>
② dataset - setAttribute("fz20")
<br>
③ innerHTML - toggleClass()
<br>
④ innerText - classList.remove("fz20")
<br>
⑤ textContent - removeClass("fz20")
<br>
<br>
<br>

  ✔️ 
  <br>
**(가) - (나)**
<br>
① dataset - removeClass("fz20")
<br>
② dataset - setAttribute("fz20")
<br>
③ innerHTML - toggleClass()
<br>

<span style="color: red;">④ innerText - classList.remove("fz20")</span>
<br>
  ❖ 기본 형태) *요소.classList.remov(클래스명);*
<br>
  ❖ 웹 요소.inner.Text - 웹 브라우저에서 보이는 내용만 가져옴
<br>
⑤ textContent - removeClass("fz20")
<br>
<br>
<br>

## 문제3 && 문제 풀이3
___
**3. 자바스크립트 코드를 작성하여 리스트를 클릭했을 때 리스트의 배경색을 yellowgreen으로 변경하시오.** <br>
> 힌트 <br>
> ol 태그를 선택한다. <br>
> ol 태그를 클릭했을 때 배경색을 yellowgreen으로 설정한다. <br>

```js
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width", initial-scale="1.0">
    <title>라면 끓이기</title>
</head>
<body>
    <h1>라면을 끓이는 순서</h1>
    <ol type="A">
        <li>물을 끓인다.</li>
        <li>라면과 스프를 넣는다.</li>
        <li>파를 썰어 넣는다.</li>
        <li>5분 후 <strong>맛있게</strong> 먹는다.</li>
    </ol>
    <script>
    // 이곳에 코드를 작성하세요.
    </script>
</body>
</html>
```

<br>
<br>
<br>

  ✔️ <br>
  
```js
const ol = document.querySelector("ol");

ol.onclick = () => {
  ol.style.backgroundColor = "yellow";
};
```
<br>
<br>
<br>
  
## 문제4 && 문제 풀이4
___
**4. 다음 코드의 입력 항목 중 나이 항목의 값을 가져오는 코드를 고르세요.** <br>

```js
<form name="frm1">
  <label for="uname">이름</label>
  <input type="text" id="uname" name="uname">
  <label for="age">나이</label>
  <input type="text" id="age" name="age">
  <button type="submit">전송</button>
</form>
```
<br>
① document.frm1.age.value
<br>
② document.forms.age.value
<br>
③ document.forms[0].uname.value
<br>
④ document.frm1.elements[0].value
<br>
⑤ document.forms[0].elements[0].value
<br>
<br>
<br>
✔️ 
<br>
<span style="color: red;">① document.frm1.age.value</span>
<br>
② document.forms.age.value
<br>
③ document.forms[0].uname.value
<br>
  ❖ 이름 값이 나옴
<br>
④ document.frm1.elements[0].value
<br>
  ❖ 이름 값이 나옴
<br>
⑤ document.forms[0].elements[0].value
<br>
  ❖ 이름 값이 나옴
<br>

④ 30</span>
<br>
❖ a=10, b=20 값이 들어가서 dosum()함수 실행.
<br>
<br>
⑤ SyntaxError
<br>
<br>

## 문제5 && 문제 풀이5
___
**5. 아래 힌트를 참고해 항목 앞에 있는 체크 표시를 누르면 항목 텍스트의 글자가** <br>
**회색(#ccc)으로 바뀌면서 가로줄이 그려지도록 자바스크립트 코드를 작성하시오.**
<br>
![첨부1](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0326_1.png?raw=true)
<br>
<br>
```js
<!DOCTYPE html>
<html lang="ko">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>연습문제 1</title>
	<style>
		ul{
			list-style: none;
		}
		li {
			font-size:20px; 
			line-height: 35px;
		}
		.check {			
			color:#ccc;
			font-size:20px;
			margin-right:25px;
		}
		.check:hover {
			color:#222;
		}
	</style>
</head>
<body>
	<h1>할 일 목록</h1>
	<ul>
		<li><span class="check">&check;</span>할 일 1 </li>
		<li><span class="check">&check;</span>할 일 2 </li>
		<li><span class="check">&check;</span>할 일 3 </li>
		<li><span class="check">&check;</span>할 일 4 </li>
		<li><span class="check">&check;</span>할 일 5 </li>
	</ul>
    <script>
        /* 이곳에 작성하시오 */
	</script>
</body>
</html>
```
<br>
<br>
<br>

  ✔️ <br>
  
```js
document.querySelectorAll(".check");
const check = document.querySelectorAll(".check");

for(let i=0;i<check.length;i++){

  
    check[i].onclick = function() {
      check[i].parentNode.style.color = "#ccc";
      check[i].parentNode.style.textDecoration = "line-through";
    }
    
}

var mother = check.parentNode;

```
<br>
<br>
<br>

