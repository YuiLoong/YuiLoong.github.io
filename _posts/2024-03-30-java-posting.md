---
categories: Java
toc: true
---

## 자바스크립트 6장 이벤트와 이벤트처리기 문제(2) 
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

* 1) <Enter> 키를 치면 어떤 키코드값이 리턴되는지는 교재 p.208페이지의 06\keycode.html을 실행하여 알아내시오. <br>
* 2) 자바스크립트에서는 문자열 형태의 수식을 쉽게 계산해주는 eval()이라는 편리한 함수가 있다.
     <br>예를 들어 eval("1+2")를 입력하면 "3"이 리턴된다.

<br>

![첨부1](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0331_1.png?raw=true)
<br>
<br>
```js
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <h1>수식 계산기</h1>
    <div>
        <label>식: <input type="text" id="question"></label>
    </div>
    <div>
        <label>답: <input type="text" id="answer"></label>
    </div>
    <script>
        // 이곳에 작성하세요.
    </script>
</body>
</html>
```
<br>
<br>
<br>

✔️
<br>
```js

 <script>
        const body = document.body;
        const question = document.querySelector("#question"); 
        const answer = document.querySelector("#answer"); 

        body.addEventListener("keydown", (e) => {
            answer.value = eval(question.value); //질문값을 가져와서 eval()함수를 이용한 값을 답 값에 넣는다.
        });

    </script>
```
<br>
<br>
<br>


## 문제3 && 문제 풀이3
___
**3. 마우스의 휠을 돌리면 wheel 이벤트가 발생한다.** <br>
**이벤트 객체의 e.wheelDelta를 통해서 마우스 휠이 움직인 방향을 알 수 있다.** <br>
**다음 프로그램을 실행해 보고 휠을 위나 아래로 돌릴때 어떤 값들이 리턴되는지 알아보시오.** <br>

```js
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        #textBox {
            border: 2px solid black;
        }
    </style>
</head>
<body>
    <div id="textBox">
        텍스트 위에서 마우스 휠을 움직이면 폰트의 크기가 증가하거나 감소합니다.
    </div>
    <script>
        const textBox = document.querySelector("#textBox");
        let size = 30;
        textBox.addEventListener("wheel", (e) => {
            if (e.wheelDelta > 0) {
                size++;
            }
            else {
                size--;
            }
            textBox.style.fontSize = size + "px";
        })
    </script>
</body>
</html>
```
<br>
<br>
<br>

  ✔️ 
  <br> 
  **해설: 휠을 위로 돌릴 때는 ( 양수 ) 값이 리턴되고, 휠을 아래로 돌릴 때는 ( 음수 ) 값이 리턴된다.**

<br>
<br>
<br>
  
