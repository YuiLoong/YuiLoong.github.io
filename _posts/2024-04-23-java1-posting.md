---
categories: Java
toc: true
---

## 자바스크립트 HTTP 통신과 JSON 문제(1)
* this list will be replaced by the table of contents
{:toc .large-only}
  <br> 
  <br>
  <br>
  <br>

## 문제1 && 문제 풀이1
___
**1.member1 변수를 JSON 문자열로 변환한 후 다시 객체로 바꿔서 member2 변수에 저장하는 소스를 작성하기** 
<br>

```js
let member1 = {name: "도레미", age: 25}
```
<br>
<br>
✔️

```js
let member2 = JSON.parse(JSON.stringify(member1));
```
<br>
<br>

## 문제2 && 문제 풀이2
___
**2.[실습] JSON 자료를 가져와 표시하기 1** 
<br>
<br>
<br>
✔️
<br>
사진으로 대체
<br>
<br>

![첨부1](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0423_1.png?raw=true)


<br>
<br>

## 문제4 && 문제 풀이4
___
**서버에 있는 JSON 자료를 가져와서 화면에 표시하려 합니다. JSON 자료에는 id를 비롯해 여러 개의 값이 담겨 있습니다.** <br>
**앞에서 공부한 XMLHttpRequest 객체를 사용해 자료를 가져와서 상품 이름과 생산 연도를 화면에 표시해 보세요.** 
<br>
<br>
<br>
✔️
<br>

**[코드]**
<br>

```js
<script>
    let xhr = new XMLHttpRequest();
    xhr.open("GET", "https://reqres.in/api/products/10");
    xhr.send();

    function renderHTML(contents){
      let output = `
        <p>상품명: ${contents.data.name}</p>
        <p>학년: ${contents.data.year}</p>
      `;
      
    document.querySelector("#result").innerHTML = output;


    }

    xhr.onreadystatechange = function() {
    if (xhr.readyState == 4 && xhr.status == 200) {
        let students = JSON.parse(xhr.responseText);
        renderHTML(students);
      }
    }

  </script>
```
<br>

**[실행결과]**
<br>


![첨부2](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0423_2.png?raw=true)

<br>
<br>

## 문제5 && 문제 풀이5
___
**5. 12\quiz-2.html 문서에는 10보다 작은 수를 입력하는 텍스트 필드가 있습니다.** <br>
**사용자가 숫자를 입력한 후 [입력] 버튼을 클릭했을 때 10보다 작은 수이면 화면에 표시하고, 10보다 큰 수를 입력했거나 아무 값도 입력하지 않았을 때,** <br>
**또는 숫자가 아닌 다른 내용을 입력했을 때 예외를 처리하는 소스를 작성해 보세요.** <br>
<br>
<br>

```js
let member1 = {name: "도레미", age: 25}
```

<br>
<br>
✔️
<br>

**[코드]**
<br>
```js
<script>
    const bttn = document.querySelector("button");
    bttn.addEventListener("click", function() {
      let value = document.querySelector("#user-number").value;
      try{
        let num = parseInt(value);
        if(num < 10){
          document.querySelector("#result").innerHTML = num;
        }else if(num >= 10){
         throw "10보다 작은 수를 입력하세요";
        }else{
          throw "숫자를 입력하세요";
        }
      }catch(error){
        alert(error);
      }
    });
    
  </script>
```
<br>

**[결과창]**
<br>

![첨부3](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0423_3.png?raw=true)
<br>
