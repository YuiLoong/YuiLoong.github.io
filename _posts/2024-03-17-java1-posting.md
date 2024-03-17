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
  > ***그래서 어떡하라고요?***
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
  <br>
  <br>
  <br>
  ![첨부1](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/20240313.jpg?raw=true)
  <br>
  ~~이 포스팅을 쓰는 와중에도 과제가 쌓여간다~~ <br>
  ~~그렇다.. 교수님 강의내용을 따라가기 위해선 어쩔 수 없는 선택이었다~~ 
  <br>
  <br>
  그리고 이번 포스팅은 왜 뻘소리가 많냐면<br>
  <br>
  <br>
  ...
  <br>
  <br>
  <br>
  <br>
  <br>
  
  >*그냥이다.*
  <br>
  
  ![첨부2](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/20240313_3.jpg?raw=true)<br>
  *개강해서 정신줄은 놓은 건 절대 아니다* <br>
  <br>
  <br>
  <br>
  <span style="color: #2D3748; background-color:#fff5b1;">정말 절대 아니고 그냥 `블로그`인데 너무 딱딱한 것 같아서 뻘소리를 좀 넣어본 것이다.</span><br>
  ~~어차피 내 블로그인데 그냥 내 마음대로 하겠습니다?~~
  <br>
  ![첨부3](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/202400313_2.jpg?raw=true)<br>
  <br>
  <br>
  <br>
  **그래봤자 이러고 다시 코드 문제에 들어가면 조용해지거나 다음 포스팅 때도 기력이 딸려서**<br>
  <br>
  
  ***다시 빡집중 모드ON*** <br>
  들어갈 수 있다. 그럴 확률 200000%이다.<br> 
  <br>
  
## 문제1
___
자신의 나이를 age 변수에 저장한 후 콘솔 창에 '나는 OO세입니다.'라고 출력하는 코드를 작성하시오.<br>
<br>

## 문제 풀이1
  ___
  콘솔 창에 출력은 console.log()를 사용하면 된다.<br>
  ```js
  let age = 20; /*age 변수에 나이를 저장*/
  console.log("나는 "+age+"세입니다.")
  ```
## 문제2
___
5개 색깔 red, blue, green, white, black 을 colors라는 배열에 저장한 후<br>
for문을 이용해  화면에 표시하는 코드를 작성하시오.<br>

## 문제 풀이2
  ___
  ```js
  const colors = ["red","blue","green","white","black"]; /*color 배열에 값을 저장*/
  for(let i = 0; i <colors.length;i++){
    document.write(`${colors[i]}. `);
  } /*배열 길이만큼 돌고 순서대로 값을 뽑는다.*/
  ```
***잠깐***
document.write()를 쓸 때는 소괄호 안에는 반드시 `백틱(backtick)`인 <span style="color: #2D3748; background-color:#fff5b1;">`</span>을 넣어줘야한다.<br>
작은 따옴표와 혼동하지 않도록<br> 

추가적으로 `for문`과 `foreach문`에 대해서도 얘기해보자면, 단순한 배열 요소라면<br> 
`for`문과 `forEach`문은 별다른 큰 차이는 없다. <span style="color: #2D3748; background-color:#fff5b1;">그러나 도중에 배열의 길이 변화로 정확한 배열 크기를 모를 때,<br>배열의 요소를 가져와 함수를 실행해야 할 때</span> `forEach`문이 더 편리하다고 볼 수 있다.
<br>

> **for문** <br>
> alert문은 알림창을 표시한다. 그리고 이 함수의 소괄호 안에 메시지나 변수를 넣으면 알림창에 텍스트나 변숫값이 뜬다.<br>
> <span style="color:green">이때 소괄호 안에 큰 따옴표나 작은 따옴표와 함께 작성해줘야한다.</span><br>

## 문제3
___
"짝수와 홀수를 구별하는 프로그램 만들기" 실습을 수행하고, 결과를 첨부하시오<br>
     
## 문제 풀이3
  ___
실습 따라하는 문제이므로 사진으로 대체한다.<br>
![첨부4](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0314_1.PNG?raw=true)<br>
![첨부5](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0314_2.PNG?raw=true)<br>

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
