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
✔️<span style="color: red;">3번</span>
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
  ✔️ 이건 예전 포스팅에서 언급한 적이 있으므로 [let과 const 차이] < 참고하면 된다.
<br>
  
[let과 const 차이]:https://yuiloong.github.io/java/2024-03-13-java-posting/#%EB%AC%B8%EC%A0%9C-%ED%92%80%EC%9D%B45
<br>
<br>

## 문제4 && 문제 풀이4
___
**4. 다음 프로그램의 실행 결과를 예측해 보시오.**
<br>
```js
console.log("\\\\\\\\");
```
<br>
<br>
<br>
  ✔️ <span style="color: red;">콘솔창에 " \\\\ " 해당 문구가 뜰 것이다(따옴표 제외)</span> <br>
  \\당 \가 출력되므로 `\`*8개로 총 4개가 출력<br> 
<br>
<br>

## 문제5 && 문제 풀이5
___
**5. 다음 프로그램에서 오류를 찾아 고치시오.**
<br>
```js
const r;
r = 10;
console.log(`넓이 = ${3.14 * r * r)`);
```
<br>
<br>
<br>
  ✔️ <span style="color: red;">const -> let으로 바꿔준다. 이유는 3번 참고.</span><br>
  
  ```js
  let r;
  r = 10;
  console.log(`넓이 = ${3.14 * r * r}`); //그리고 오탈자인진 모르겠으나 ) -> }로도 바꿔야됨
  ```
<br>
<br>
## 문제6 && 문제 풀이6
___
**6. 다음 중 데이터의 종류와 자료형이 잘못 짝지어진 것을 고르시오.**
<br>
(1) 문자열 - "Hello, Javascript" <br>
(2) 숫자형 - 0.11121212 <br>
(3) 논리형 - true <br>
(4) undefined - undefined <br>
(5) 배열 - { } <br>
<br>
<br>
<br>

  ✔️ <span style="color: red;">5번</span> <br>
  배열은 `[]` 이다.<br> 
<br>
<br>

## 문제7 && 문제 풀이7
___
**7. 다음 코드의 실행 결과를 적으시오.**
<br>
| 코드                           | 결과           | 해설
|:-------------------------------|:---------------|:----------------------------------------------
| console.log(52 + 273);         | 325            | 숫자+숫자=숫자
| console.log("52" + 273);       | "52273"        | 문자+숫자=(통합하고)문자
| console.log(52 + "273");       | "52273"        | 숫자+문자=(통합하고)문자 
| console.log("52" + "273");     | "52273"        | 문자+숫자=(통합하고)문자
| console.log(10 + 20 + '!!!!'); | "30!!!!"       | (숫자+숫자)+문자=문자
<br>
<br>
<br>
  ✔️ <span style="color: red;">콘솔창에 " \\\\ " 해당 문구가 뜰 것이다(따옴표 제외)</span> <br>
  \\당 \가 출력되므로 `\`*8개로 총 4개가 출력<br> 
<br>
<br>
## 문제8 && 문제 풀이8
___
**8. 다음 프로그램의 실행 결과를 예측해 보시오.**
<br>

```js
console.log("안녕하세요"[1]);
console.log("안녕하세요"[2]);
console.log("안녕하세요"[3]);
console.log("안녕하세요"[4]);
```
<br>
<br>
<br>
  ✔️ <span style="color: red;">콘솔창에 " 녕 하 세 요 " 해당 문구가 뜰 것이다(따옴표 제외)</span> <br>
  배열로 생각하고 순서대로 0번째부터 시작한다고 보고 1번째인 `녕`<br>
  2번째인 `하` ... 이렇게 출력이 된다.
<br>
<br>

## 문제9 && 문제 풀이9
___
**9. 사용자로부터 원의 반지름을 입력받아 원의 넓이와 둘레를 구하는 프로그램을 작성하시오.** <br>
**(참고: 원의 넓이 = 3.14 * r * r, 원의 둘레 = 2 * 3.14 * r)**
<br>
<br>
<br>
✔️  
1. 콘솔창으로 출력하는 건지 알림창으로 하는 건지 <br>
2. 소수점 어느자리까지 표시하는 지 <br>
애매해서 임의로 정했다. 알림창으로 입력값을 받아 알림창에 표시하는 프로그램을 짜보겠다.<br>
```js
let r = prompt("원의 반지름을 입력하세요");
let s = 3.14*r*r;
let l = 3.14*2*r;

alert(`넓이: ${s}, 둘레: ${l}`); 
```
<br>
<br>
✔️ 결과창<br> 

![첨부4](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0317_1.png?raw=true)
![첨부5](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0317_2.png?raw=true)
