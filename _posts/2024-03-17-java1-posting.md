---
categories: Java
toc: true
---

## 자바스크립트 변와 자료형 문제(1)
  <br> 
  <br>
  <br>
  <br>
  > <span style="color: red;">***(경) 시작하기 앞서, 경사났다. (축)*** </span><br>
  <br>
  
  ![첨부1](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/20240317_3.jpg?raw=true)
  <br>
  <br>
  <br>
  
  **포스팅 쓰는 도중에 글이 싹다 날라가서 다시 씁니다!! ~~하하핳 안 웃겨요.~~** <br>
  멘탈 나갔지만..다시 써보겠습니다.<br>
  <br>
  <br>
  맙소사. 이런 상황에서 감기까지 걸렸습니다<br>
  금요일날 서울 갔더니 감기 기운을 주더라고요? 서울특별시 진짜 안 감사합니다.<br>
  근데 집에 돌아왔더니 가족이 감기에 걸려와서 제대로 옮아버렸습니다.<br>
  "감기 걸리면 안되는데..."하고 걱정하고 있었는데<br>
  괜한 걱정하지말라고 감기 바이러스를 준 우리가족 감사합니다!<br>
  요즘 감기가 유행인가?<br>
  <br>
  ![첨부2](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/20240317_1.jpg?raw=true)
  <br>
  <br>
  너무 아파서 앓다가 밤에 목이 너무 따가워서 잠도 못 자는 저런 상황이 발생해버렸는데.<br>
  <br>
  <br>
  > ***그래서 어떡하라고요?*** <br>
    ㄴ정신차려보니(~~아직도 못차림~~) 과제 제출기간이 얼마 안 남아서 요지경이 되어버렸어요~!ㅎㅎ<br>  
  ![첨부3](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/20240317_2.png?raw=true)
  <br>
  <br>
  그래서 하고 싶은 말은 한동안 아파서 좀 딱딱한 방식으로 포스팅을 쓸 것 같아요<br>
  지금은 도중에 글을 날렸다는 이유로 분노의 포스팅 중(장난인 거 아시죠?ㅎㅎ~~장난아닌 것 같다고요? 네 맞아요~~) <br>
  아무튼 주절주절 얘기하는 거 없이 갈게요..~~슬슬 주절주절거리느라 타이핑 시간 많이 들고 귀찮아서 그러는 거 절대 맞음~~
  <br>
  <br>
  <br>
 
  
## 문제1 && 문제 풀이1
___
**1. 다음 중 변수명으로 사용할 수 없는 것을 고르시오.** <br>
**(1) a (2) hello (3) 10times (4) _ (5) $**
<br>
<br>
<br>
✔️<span style="color: red;">3)</span>
<br>
>**자바스크립트의 규칙은 이렇다.** <br>
>> 변수명 '첫글자'는 `영문자`/`$`/`_`(언더바)만 올 수 있다. <br>
>> 변수명 첫글자 이후로는 `영문자`/<span style="color: green;">`숫자`</span>/`$`/`_`(언더바)만 올 수 있다. <br>
<br>
<br>
  그러므로 첫글자가 숫자인 3번이 오답. <br>
<br>

## 문제2 && 문제 풀이2
___
**2. 변수 score를 선언해서 데이터 10을 할당하는 코드를 작성해 보시오.**
<br>
<br>
<br>
  ✔️ 
  ```js
  let score = 10;
  ```
<br>
<br>

## 문제3 && 문제 풀이3
___
**3. var와 let과의 차이, let과 const와의 차이를 간략하게 설명하시오.**
<br>
<br>
<br>
  ✔️ 
  ```js
  let score = 10;
  ```
<br>
<br>

## 문제4
___
5개 과일 apple, banana, cheery , grape, orange를 fruits라는 배열에 저장한 후 forEach 문을 이용해  화면에 표시하는 코드를 작성하시오.<br>

## 문제 풀이4
  ___
```js
const fruits = ["apple","banana","cheery","grape","orange"];

/*1*/
fruits.forEach(function(fruit){
  document.write(`${fruit}.`)
});

/* 1번 부분은 아래 코드와 같이도 쓸 수 있다.
fruits.forEach(fruit => document.write(`${fruit}. `});
*/
```

<br>

## 문제5
