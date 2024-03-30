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
**1. 버튼을 더블 클릭하면 경고창이 출력되게 코드를 작성해 주세요. 이때, 경고창의 메시지는 아무거나 상관없습니다.** <br>
* 힌트: 교재  p.194의 표에서 더블 클릭의 이벤트명이 무엇인지 찾아보세요. <br>

```js
<button>클릭</button>
<script>
  // 코드를 작성해 주세요.
</script>
```
<br>
<br>
<br>
✔️
<br>

```js
<button>클릭</button>
<script>
  const button = document.querySelector("button");

  button.ondblclick = function(){
    alert("경고! 경고! 누르지마세요!")
  }
</script>
```
<br>
<br>

## 문제2 && 문제 풀이2
___
**2. 계산식을 입력받아 결과를 출력하는 웹 페이지를 작성하시오.** <br>
**식 입력 후 <Enter> 키를 치면 수식을 계산하고 결과를 출력해야 한다.** <br>
>**힌트:** <br>

* 1) <Enter> 키를 치면 어떤 키코드값이 리턴되는지는 교재 p.208페이지의 06\keycode.html을 실행하여 알아내시오.
<br>
* 2) 자바스크립트에서는 문자열 형태의 수식을 쉽게 계산해주는 eval()이라는 편리한 함수가 있다.
     <br>예를 들어 eval("1+2")를 입력하면 "3"이 리턴된다.

<br>
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
