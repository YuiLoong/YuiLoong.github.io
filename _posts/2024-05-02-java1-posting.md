---
categories: Java
toc: true
---

## 스프링부트 1장 실습(1)
* this list will be replaced by the table of contents
{:toc .large-only}
  <br> 
  <br>
  <br>
  <br>

## 문제1 && 문제 풀이1
___
**1.localhost:8080/hello.html과 같이 웹 사이트 주소에 파일명을 직접 명시한 경우 서버는 어떤 디렉터리에서 파일을 찾을까요?** <br>

1) src > main > java
<br>
2) src > main > java > com.example.firstproject
<br>
3) src > main > resources
<br>
4) src > main > resources > static
<br>
<br>
<br>
✔️
<br>
**[코드]**
<br>

```js
  <script>
    fetch("https://dummyjson.com/quotes")
    .then(response => response.json())
    .then(qutoes => console.log(qutoes));
  </script>
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
```js
<script>
    fetch("https://dummyjson.com/quotes")
    .then(response => response.json())
    .then(qutoes => {
      const idx = Math.floor(Math.random()*30);
      const quote = qutoes.quotes[idx];

    console.log(quote)
    document.querySelector(".quote").innerHTML = quote.quote;
    document.querySelector(".author").innerHTML = quote.author;
    });
    
  </script>
```
<br>
<br>

![첨부1](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0423_1.png?raw=true)


<br>
<br>
