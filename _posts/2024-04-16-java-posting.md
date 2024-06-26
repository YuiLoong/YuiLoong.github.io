---
categories: Java
toc: true
---

## 자바스크립트 10장 문자열과 배열 활용 문제(1) 
* this list will be replaced by the table of contents
{:toc .large-only}
  <br> 
  <br>
  <br>
  <br>
 

## 문제1 && 문제 풀이1
___
**1. charAt() 메서드를 사용해서 greeting 변수의 세 번째 문자에 접근하는 소스를 작성해보세요.** <br>
<br>
<br>

✔️
<br>

**[코드]** <br>

```js
greeting.charAt(2);
```
<br> 
<br>

## 문제2 && 문제 풀이2
___
**2. 교재 p.340의 소스에서 if 문에 대괄호 대신 charAt() 메서드를 사용하시오.** <br>
<br>
<br>

✔️
<br>

**[코드]** <br>

```js
if(str[i] == ch ) --> if(str.charAt(i) == ch)
```
<br>
<br>
<br>

## 문제3 && 문제 풀이3
___
**3. str1 문자열에서 문자열 "everyone"이 어느 위치에서 나타나는지 찾아보세요.** <br>
<br>
<br>

✔️
<br>

**[코드]** <br>

```js
str1.indexOf("everyone");
```
<br>
<br>
<br>

## 문제4 && 문제 풀이4
___
**4. "good moring".startWith("o", 2)의 결과 값은?** <br>
<br>
<br>

✔️
<br>
**답: True**
<br>
<br>
<br>



## 문제5 && 문제 풀이5
___
**5. "Hello, everyone.".endwidth("l", 4)의 결과 값는?** <br>
<br>
<br>

✔️
<br>
**답: True**
<br>
해설: `endwidth`는 1부터 시작함
<br>
<br>
<br>

## 문제6 && 문제 풀이6
___
**6. str2 문자열에 one이 포함되어 있는 지 확인하는 소스를 작성해 보세요.** <br>
<br>
<br>

✔️
<br>

**[코드]** <br>

```js
str2.includes("one");
```
<br>
<br>
<br>

## 문제7 && 문제 풀이7
___
**7. "Hello, everyone." 문자열에서 everyone.만 추출해 보세요.** <br>
<br>
<br>

✔️
<br>

**[코드]** <br>

```js
"Hello, everyone.".substring(7);
```
<br>
<br>
<br>

## 문제8 && 문제 풀이8
___
**8. 다음 소스코드를 실행했을 때 결과값은?** <br>

```js
let arr = [0, 1, 2, 3, 4, 5];
arr.slice(-1);
```
<br>
<br>
<br>
✔️
<br>

**답: [5]**
<br>
<br>
<br>

## 문제9 && 문제 풀이9
___
**9. 웹 주소 웹 주소 https://cafe.naver.com/doitstudyroom 을 프로토콜과 도메인, 페이지로 구분하시오. 이때 구분자로 /를 사용하시오** <br>
<br>
<br>
✔️
<br>

**코드: https://cafe.naver.com/doitstudyroom.split("/");**
<br>

**결과: ["https:","","cafe.naver.com","doitstudyroom"]**
<br>
<br>
<br>

## 문제10 && 문제 풀이10
___
**10. 보안을 위해 이메일 주소의 일부 감추기** 
<br>
<br>
<br>
✔️
<br>

**코드**
```js
<script>
    let result = document.querySelector("#result");
    const button = document.querySelector("button")
    button.addEventListener("click", function(){
    const email = document.querySelector("#userEmail").value;
    let first = email.split("@");
    let id = first[0];
    let domain = first[1];

    id = id.substring(0,3);
    result.innerText = `${id} ...@${domain}`;

    });
  </script>
```
<br>

**결과창**
<br>
![첨부1](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0416_1.png?raw=true)
<br>
<br>

## 문제11 && 문제 풀이11
___
**11. 영문자열의 첫 번째 글자를 대문자로 바꾸기** <br>
<br>
<br>
✔️
<br>
**코드**
<br>

```js
const result = [string[0].toUpperCase(), ...string.slice(1)].join("");
```
<br>
<br>

## 문제12 && 문제 풀이12
___
**12. 전개 연산자를 사용해 vegitable 배열과 cheese 배열을 합친 후에 맨 마지막에 빵까지 합쳐서 cheeseBurger2 배열을 만들기** <br>
<br>
<br>
✔️
<br>
**코드**
<br>

```js
let cheeseBurger2 = [...vegitable, ...cheese,"빵"]
```
<br>
<br>

## 문제13 && 문제 풀이13
___
**13. slice() 함수를 사용해 colors 배열에서 blue와 white를 추출하시오.** <br>

<br>
<br>
✔️
<br>

**코드**
<br>
```js
let colors = ["red","green","blue","white","black"];
let newColors = colors.slice(2,4);
```
<br>
<br>
<br>

## 문제14 && 문제 풀이14
___
**14. 10\quiz-1.html 문서에는 [2, 4, 6, 8, 10]이라는 배열이 있는데,** <br>
**이 배열을 화면에 표시하고 배열의 요소를 모두 더한 후 마지막에 결괏값을 추가하는 프로그램을 작성하시오.** <br>

<br>
<br>
✔️
<br>

**코드**
<br>
```js
<script>
    const origin = document.querySelector("#origin");
    const result = document.querySelector("#result");

    function Arr(area, array){
      let text = "<table><tr>";
      for (let i=0; i<array.length;i++){
        text += `<td>${array[i]}</td>`;
      }
      text += "</tr></table>";
      area.innerHTML = text;
    }
    const arr = [2,4,6,8,10];
    Arr(origin,arr);

    let sum=0;
    for(let i=0;i<arr.length;i++){
      sum+=arr[i];
    }
    arr.push(sum);
    Arr(result,arr);
  </script>
```
<br>

**결과창**
<br>

![첨부1](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0416_2.png?raw=true)
<br>
<br>
<br>

## 문제15 && 문제 풀이15
___
**15. 10\js\quiz-2.js 파일에 작성한 다음의 소스를 참고해서 tail() 함수를 작성하기** <br>
**tail() 함수는 배열을 받아서 배열의 길이가 1보다 크면 첫 번째 요소를 뺀 나머지 요소를,** <br>
**배열의 길이가 1이면 배열 전체를 반환합니다.** <br>

<br>
<br>
✔️
<br>

**코드**
<br>
```js
const origin = document.querySelector("#origin");
const result = document.querySelector("#result");

let numbers = [2, 4, 6, 8, 10];

//함수 추가
const tail = (arr => arr.length > 1 ? arr.slice(1) : arr);

origin.innerText = numbers;
result.innerText = tail(numbers);

```
<br>

**결과창**
<br>
![첨부15](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0416_15.png?raw=true)
<br>
<br>
