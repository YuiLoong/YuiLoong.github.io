---
categories: Java
toc: true
---

## 자바스크립트 7장 DOM 활용하기 문제(1) 
* this list will be replaced by the table of contents
{:toc .large-only}
  <br> 
  <br>
  <br>
  <br>
 

## 문제1 && 문제 풀이1
___
**1. 장바구니에 상품 추가하기 실습** <br>
<br>
<br>
✔️
<br>
**[코드]** <br>


```js
 <script>
    const orderButton = document.querySelector("#order");
    const orderInfo = document.querySelector("#orderInfo");
    const title = document.querySelector("#container > h2");
    orderButton.addEventListener("click", ()=> {
      let newP = document.createElement("P");
      let textNode = document.createTextNode(title.innerText);
      newP.appendChild(textNode);
      orderInfo.appendChild(newP);
    })
  </script>
```
<br>

**[결과창]** <br> 

![첨부1](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0402_1.png?raw=true)
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


## 문제3 && 문제 풀이3
___
**3. 모달 박스 만들기 실습.** <br>
<br>
<br>

  ✔️ 
  <br> 실습 따라하기이므로 결과물로 대체 <br>
  
  
![첨부1](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0330_1.png?raw=true)
<br>
<br>
<br>
  
## 문제4 && 문제 풀이4
___
**4. 나만의 도서 목록 만들기 실습** <br>
<br>
<br>
✔️ 
<br>

**[코드]** <br>

```js
<script>
    const title = document.querySelector("#title");
    const author = document.querySelector("#author");
    const save = document.querySelector("#save");
    const bookList = document.querySelector("#bookList");

    save.addEventListener("click", function(e){
      e.preventDefault(); //form에 이벤트가 가는 것을 막는다.
      const item = document.createElement("li");
      item.innerHTML = `${title.value} - ${author.value}
      <span class = "delButton">삭제 </span>`;
      bookList.appendChild(item);
      title.value ="";
      author.value="";
      
      //삭제 버튼 만들기
      const delButtons = document.querySelectorAll(".delButton");
      delButtons[delButtons.length-1].addEventListener("click", function(){
        this.parentNode.remove();
      })
      // for(let delButton of delButtons){
      //   delButton.addEventListener("click", function(){
      //     this.parentNode.remove();
      //   })
      // }
    });
  </script>
```

**[결과창]** <br>

![첨부3](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0402_3.png?raw=true)
<br>
<br>

## 문제5 && 문제 풀이5
___
**5. 자바스크립트로 캐러셀 만들기 실습** 
<br>
<br>
<br>

  ✔️ <br> 실습 따라하기이므로 결과물로 대체 <br>
  

![첨부2](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0330_2.png?raw=true)

<br>
<br>
<br>

## 문제6 && 문제 풀이6
___
**6. 06\quiz-1.html 문서에는 하나의 이미지가 삽입되어 있습니다. 이 이미지의 위에 마우스 포인터를 올려 놓았을 때** <br>
**06\images\pic-6.jpg로 바뀌었다가 마우스 포인터를 다른 곳으로 이동하면 06\images\pic-1.jpg로 바뀌는 소스를 작성.** <br>

>**사용할 파일** <br>

 * 06\quiz-1.html <br>
 * 06\js\quiz-1.js (신규 작성) <br>
<br>

>**힌트** <br>

 * 06\quiz-1.html 문서에서 <img> 태그에는 id나 class가 없습니다.<br>
 * 태그 이름을 사용하거나 2개 이상의 선택자를 연결한 후 이미지를 가져와서 변수에 저장합니다. <br>
 * 마우스 포인터를 이미지의 위에 올려 놓을 때는 mouseover 이벤트가, 마우스 포인터를 다른 곳으로 이동할 때는 mouseout 이벤트가 발생합니다.<br>
 * 이벤트가 발생했을 때 이미지의 src 속성값을 바꿉니다. <br>

<br>
<br>
✔️
<br>

```js
 <style>
    #container {
      width: 600px;
      margin: 20px auto;
    }
    h1 {
      font-size:1.5rem;
      text-align:center;
      margin-bottom:20px;
    }
  </style>
</head>
<body>
  <div id="container">
    <h1>마우스 오버하면 이미지 바꾸기</h1>
    <img src="images/pic-1.jpg" alt="">
  </div>
  <script>
    const img = document.querySelector("img");
    img.addEventListener("mouseover", () => {
      img.src = "images/pic-6.jpg";
    });
    img.addEventListener("mouseout", () => {
      img.src = "images/pic-1.jpg";
    });
  </script>
</body>

```
<br>
<br>

## 문제7 && 문제 풀이7
___
**7. 이벤트를 활용해 따라 표시했다가 감추는 메뉴를 만들어 보자. 여기에서는 아이콘을 클릭하면 메뉴가 표시되고,** <br>
**다시 클릭하면 메뉴가 숨겨지는 예제를 만들 것이다. 06\css\solution-2.css 파일에는** <br>
**버튼과 메뉴에서 사용할 .active 스타일이 미리 만들어져 있습니다. 버튼을 클릭할 때마다 변수와 메뉴에 .active 스타일을 토글하는 소스를 만들기** <br>
>**사용할 파일** <br>

 * 06\quiz-2.html <br>
 * 06\js\quiz-2.js (신규 작성) <br>
<br>

>**힌트** <br>

 * 웹 문서에 연결된 외부 스타일 시트 파일에 button.active와 nav.active 스타일이 미리 만들어져 있습니다. <br>
 * 버튼과 메뉴를 가져와서 각각 변수로 저장합니다.<br>
 * 버튼에 click 이벤트가 발생했을 때 실행할 함수를 연결하는데, 이 함수에서는 버튼과 메뉴에 active 클래스 스타일을 토글합니다. <br>
<br>
<br>

✔️
<br>

```js
 <link rel="stylesheet" href="css/solution-2.css">
</head>
<body>
  <button id="bttn">&#9776;</button>

  <nav id="nav">
    <ul>
      <li><a href="#">Javascript</a></li>
      <li><a href="#">Typescript</a></li>
      <li><a href="#">Node.js</a></li>
    </ul>
  </nav>
  <script>
    const bttn = document.querySelector("#bttn");
    const nav = document.querySelector("#nav");
    bttn.addEventListener("click",() => {
      bttn.classList.toggle("active");
      nav.classList.toggle("active");
    });
  </script>
```
<br>
<br>
