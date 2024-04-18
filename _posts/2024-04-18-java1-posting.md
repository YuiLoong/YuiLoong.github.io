---
categories: Java
toc: true
---

## 자바스크립트 문자열과 배열 활용하기 문제(2)
* this list will be replaced by the table of contents
{:toc .large-only}
  <br> 
  <br>
  <br>
  <br>

## 문제1 && 문제 풀이1
___
**1.다음 배열에 대한 설명 중 틀린 것은?** 
<br>

```js
let months = new Array("Jan", "Feb", "March");
```
<br>
① let months = ["Jan", "Feb", "March"]; 로 대신할 수 있다.
<br>
② months.length는 3이다.
<br>
③ months[1] = "Februray"; 코드는 "Feb"를 "Februray"로 수정한다.
<br>
④ months.length = 5로 지정하여 배열의 크기를 5개로 늘릴 수 없다.
<br>
<br>
<br>
✔️

<span style="color: red;">④ months.length = 5로 지정하여 배열의 크기를 5개로 늘릴 수 없다.</span>
<br>
❖ 길이를 변경할 수 있다.
<br>
<br>

## 문제2 && 문제 풀이2
___
**2.다음 배열에 대한 설명 중 틀린 것은?**
<br>
```js
let grades = new Array("A", "B", "C", "D");
```
<br>
① grades[4] = "F";를 실행하면 grades 배열의 크기가 1 늘어난다.
<br>
② grades[3] = 70;은 잘못된 코드이다. 왜냐면 문자열 배열에 정수를 넣었기 때문.
<br>
③ grades.reverse()를 호출한 결과 grades 배열 내부가 ["D", "C", "B", "A"]로 변한다.
<br>
④ grades.length는 4이다.
<br>
<br>
<br>

  ✔️ 
  <br>
<span style="color: red;">② grades[3] = 70;은 잘못된 코드이다. 왜냐면 문자열 배열에 정수를 넣었기 때문.</span>
<br>
❖ 타입형이 없기 때문에 딱히 잘못된 코드는 아니다.
<br>
<br>
<br>

## 문제3 && 문제 풀이3
___
**3.주석에 맞게 다음 빈 칸을 채우시오.** <br>
```js
let ______________________________               // Array를 이용하여 크기가 3인 배열 money 생성
_____________________________ = 5;               // money의 첫 번째 요소에 5 삽입
_____________________________ = 7;               // money의 두 번째 요소에 7 삽입
_____________________________ = -3;              // money의 세 번째 요소에 -3 삽입
let sum = 0;
for (let i=0; i<_______________; i++) sum += money[i];     // 배열 합 구하기
document.write(________________);                // 평균 출력
```
<br>
<br>
<br>

  ✔️ <br>
  
```js
let money = new Array(3);
money[0] = 5;
money[1] = 7;
money[2] = -3;
let sum = 0;
for(let i=0; i<money.length;i++) sum+= money[i];
document.write(sum/3);
```
<br>
<br>
<br>
  
## 문제4 && 문제 풀이4
___
**4. 다음의 자바 스크립트 코드가 있을 때 아래 각 항목의 실행 결과 변수 x의 값은 무엇인가?** <br>

```js
let text = "Web Programming";
```
<br>
<br>
<br>
✔️ 
<br>


|                  코드                 |      X 값         
|:--------------------------------------|:-----------------
| let x = text.length;                  | 15        
| let x = text[2];                      | "b"               
| let x = text.split(" ").length;       | 2
| let x = text.replace("web", "HTML5"); | HTML5 Programing
| let x = text.charAt(4);               | "P"

<br>
<br>

## 문제5 && 문제 풀이5
___
**prompt 함수를 호출하여 사용자로부터 문자열을 입력받고,** <br>
**"&" 문자를 기준으로 분할하여 출력하는 웹 페이지를 작성하시오.**
<br>

![첨부1](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0418_1.png?raw=true)
<br>
<br>

```js
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=<device-width>, initial-scale=1.0">
    <title>Document</title>
    <style>
        #container {
          width:500px;
          margin:20px auto;
        }
    </style>
</head>
<body>
    <div id="container">
        <h1>문자열 분할</h1>
        <ul id="result">

        </ul>
    </div>
    <script>
        // 이곳에 작성하세요
    </script>
</body>
</html>
```
<br>

  ✔️ <br>
  
```js
<script>
        //입력값 받기
        let input = prompt("문자열을 입력하시오");
        // "&"로 나누기
        let parts = input.split("&");

        let list = document.querySelector("#result");
        for(let i=0;i<parts.length;i++){
            let li = document.createElement("li");
            li.innerText = parts[i];
            list.appendChild(li);
        }
    </script>
}

```
<br>

![첨부2](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0418_2.png?raw=true)
<br>
![첨부3](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0418_3.png?raw=true)
<br>

