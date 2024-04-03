---
categories: Java
toc: true
---

## 자바스크립트 7장 DOM 활용하기 문제(2) 
* this list will be replaced by the table of contents
{:toc .large-only}
  <br> 
  <br>
  <br>
  <br>
 

## 문제1 && 문제 풀이1
___
**1. 공부할 주제를 입력하고 추가 버튼을 누르면 화면에 입력값이 계속 추가되어 나타나고,** <br>
**입력값을 클릭하면 없어지도록 만들어 보시오.** <br>

![첨부1](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0404_1.png?raw=true)
<br>
![첨부2](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0404_2.png?raw=true)
<br>
<br>

>**힌트** <br>

 * button 요소의 onclick 속성에 newRegister()라는 자바스크립트 함수가 할당되어 있으므로, <br>
 `<script>` 부분에 `newRegister()`라는 함수를 작성한다.<br>
 * input 요소에 입력된 값을 가져온다. <br>
 * 출력할 요소로 itemList를 선택한다. <br>
 * ul 요소안에 놓일 요소이므로 li 노드를 생한다.<br>
 * li 노드의 텍스트로  input 요소에 입력된 값을 할당한다. <br>
 * li 노드의 onclick 속성에 또는 이벤트 리스너를 만들어 자기자신을 삭제하는 코드를 할당한다. <br>
   자기자신을 삭제하는 코드는 자신의 부모를 찾아 자식으로서 자신을 삭제하는 것으로 익명함수로 처리한다. <br>
 * itemList의 자식 노드로 li 요소를 연결한다. <br>
 * 다음 사용을 위해 input 요소에 입력된 값은 지운다. <br>
<br>
	 
```js
<!DOCTYPE html>
<html lang="ko">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>Web Programming</title>
	<link rel="stylesheet" href="css/nodelist.css">
</head>
<body>
  <div id="container">
    <h1>Web Programming</h1>
    <p>공부할 주제를 기록해 보세요</p>
    <form action="">
      <input type="text" id="subject" autofocus>
      <button onclick="newRegister(); return false;">추가</button>
    </form>
    <hr>  
    <ul id="itemList">
  
    </ul>  
  </div>
  <script>
    // 여기에 코드를 추가하세요.
  </script>
</body>
</html>
```



<br>
<br>
✔️
<br>
**[코드]** <br>


```js
 <script>
    function newRegister(){
        const subject = document.querySelector("#subject").value;
        const itemList = document.querySelector("#itemList");

        const liNode = document.createElement("li");
        // liNodeText = document.createTextNode(subject.innerText);

        liNode.textContent = subject;

        liNode.addEventListener("click", function(e){
            e.preventDefault();
            this.parentNode.removeChile(this);
        });

        itemList.appendChild(liNode);
        document.querySelector("#subjet").value="";


    }
  </script>
```
<br>

**[결과창]** <br> 

<br>

## 문제2 && 문제 풀이2
___
**2. 시간에 따라 다른 이미지 표시하기 실습** <br>

<br>
<br>
✔️

<br>

**[코드]** <br>

```js
 <script>
    const today = new Date();
    const hrs = today.getHours();
    let newImg = document.createElement("img");
    newImg.src = (hrs < 12)? "images/morning.jpg":"images/afternoon.jpg";
    const container = document.querySelector("#container");
    container.appendChild(newImg);

  </script>
```
<br>

**[결과창]** <br>

![첨부2](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0402_2.png?raw=true)
<br>
<br>
