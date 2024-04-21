---
categories: Java
toc: true
---

## 자바스크립트 배열과 객체 더 깊게 살펴보 문제(2)
* this list will be replaced by the table of contents
{:toc .large-only}
  <br> 
  <br>
  <br>
  <br>

## 문제1 && 문제 풀이1
___
**1.도시 이름이 들어 있는 배열 cities는 다음과 같다.** 
<br>
```js
let cities = ["서울", "베를린", "리오데자네이루", "코펜하겐", "로스엔젤레스"];
```
<br>

> 다음 문항에서 요구하는 자바스크립트 코드를 작성하되, for 문과 같은 반복문을 사용하지않기. <br>
> 1) cities 배열에 들어 있는 도시 이름들을 출력하시오. <br>
> 2) cities 배열에 서 가장 긴 도시 이름을 출력하시오. <br>
> 3) cities 배열에서 가나다 순으로 가장 먼저 나오는 도시 이름을 출력하시오.

<br>
<br>

**[코드]**
<br>
```js
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=<device-width>, initial-scale=1.0">
    <title>Document</title>
    <style>
        container{
            width:600px;
            margin:20px auto;
        }
        h1 {
            font-size:1.5em;
        }
        li {
            font-size:1rem;
            line-height: 2;
        }
    </style>
</head>
<body>
    <div id="container">
        <h1>문자열 배열 다루기</h1>
        <ul id="result">
        </ul>
    </div>
    <script>
        // 이 곳에 작성하세요
    </script>
</body>
</html>
```
<br>

**[요구 결과]**
<br>
![첨부1](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0421_1.png?raw=true)
<br>
<br>
<br>

✔️
<br>

**[코드]**
<br>

```js
<script>
        let cities = ["서울", "베를린", "리오데자네이루", "코펜하겐", "로스엔젤레스"];

        const result1 = document.querySelector("#result");
        result1.innerHTML = `<li> 도시 전체 이름: ${cities.join()} </li>`; //1번

        //2번
        const long = cities.reduce((longest, current) => {
            return current.length > longest.length ? current : longest;
        }, "");

        const result2 = document.createElement("li");
        result2.textContent = `가장 긴 도시 이름: ${long}`;
        result1.appendChild(result2);

        //3번
        cities.sort();
        
        const result3 = document.createElement("li");
        result3.textContent = `가나다 순으로 먼저 나오는 도시 이름: ${cities[0]}`;
        result1.appendChild(result3);
    </script>
```
<br>

**[결과창]**
<br>
![첨부2](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0421_2.png?raw=true)

<br>
