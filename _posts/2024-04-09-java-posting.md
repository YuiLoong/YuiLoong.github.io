---
categories: Java
toc: true
---

## 자바스크립트 8장 내장 객체 문제(1) 
* this list will be replaced by the table of contents
{:toc .large-only}
  <br> 
  <br>
  <br>
  <br>
 

## 문제1 && 문제 풀이1
___
**1. 자신의 생일을 사용해 Date 인스턴스를 만들고 birthDay라는 변수로 설정해 보세요.** <br>
<br>
<br>

✔️
<br>

**[코드]** <br>
```js
 let birthDay = new Date("0000-08-07")
```
<br> 
<br>

## 문제2 && 문제 풀이2
___
**2. 만 보 걷기, 오늘까지 며칠째일까?** <br>
<br>
<br>
✔️

<br>

**[코드]** <br>

```js
 const firstDay = new Date("2024-01-01");
    const today = new Date();

    let diff = (today.getTime()-firstDay.getTime()) / (24*60*60*1000);
    document.querySelector("#result").innerHTML = Math.round(diff);
```
<br>

**[결과창]** <br>

![첨부1](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0409_1.png?raw=true)
<br>
<br>
