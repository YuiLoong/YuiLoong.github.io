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

**답: 5**
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

**코드: https://cafe.naver.com/doitstudyroom.split("/");**
**결과: ["https:","","cafe.naver.com","doitstudyroom"]**
<br>
<br>
<br>
