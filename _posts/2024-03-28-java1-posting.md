---
categories: Java
toc: true
---

## 자바스크립트 6장 이벤트와 이벤트처리기 문제(1) 
* this list will be replaced by the table of contents
{:toc .large-only}
  <br> 
  <br>
  <br>
  <br>
 

## 문제1 && 문제 풀이1
___
**1. 06\js\event-2.js 나 event-3.js 를 참고해서 [Click] 버튼을 클릭했을 때 문서의 배경색은 #222로, 글자색은 #fff로 변경하는 소스를 작성해 보세요.** <br>
**이때 웹 문서에 약간의 텍스트가 있어야 글자색이 바뀌는 것을 확인할 수 있는데, 문서의 텍스트는 직접 입력하세요.** <br>
**작성할 파일 - 06\q0.html, 06\js\q01.js** <br>
<br>
<br>
✔️
<br>
```js
 <script>
    const button = document.querySelector("button");
    button.addEventListener("click",() => {
      document.body.classList.toggle("convert");
    })
  </script>
```
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
**4. 06\js\event-6.js 파일을 참고해 사각형 영역에서 마우스를 움직일 때** <br>
**즉, mousemove 이벤트가 발생할 때 이벤트의 발생 위치를 콘솔 창에 보여주는 소스를 작성해 보세요** <br>
> mouse 이벤트 종류는 p.194 표 5-2 참고 <br>
> 작성파일 <br>
 - 06\q04.html (06\event-6.html을 복사해 수정) <br>
 - 06\js\q06.js <br>

<br>
<br>
✔️ 
<br>
```js
<link rel="stylesheet" href="css/main.css">
  <style>
    p {
      font-size:1.2rem;
      margin-bottom:20px;
    }
    #box{
      width:200px;
      height:200px;
      border:1px solid #222;
      border-radius:5%;
    }

  </style>
</head>
<body>
  <p>사각형 내부를 클릭해 보세요</p>
  <div id="box"></div>
  <script>
    const box = document.querySelector("#box");
    box.addEventListener("mousemove",(e)=>{
      console.log(`(${e.pageX},${e.pageY})`);
    })
  </script>
</body>
```
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
