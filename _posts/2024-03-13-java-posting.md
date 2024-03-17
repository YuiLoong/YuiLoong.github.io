---
categories: Java
toc: true
---

## 자바스크립트 변수와 자료형 연습문제(1)
  올해부턴 자바뿐만 아니라 `자바스크립트`를 공부하며 문제를 풀어나가 보려고 한다.<br>
  ~~한 것도 없는데 벌써 24년도 3월이랜다 올해는 진짜 정말 열심히 살아보도록 노력해야지 ..~~ <br>
  <br>
  이번 포스팅부턴 문제당 1포스팅이 아니라 <span style="color: #2D3748; background-color:#fff5b1;">한 포스팅에 여러문제</span>를 풀면서 공부하려고 합니다.
  <br>
  
## 문제1
___
알림창에 자신의 이름을 출력하는 코드를 작성해 보시오<br>
<br>
<br>

## 문제 풀이1
  ___
  먼저 `Visual Code`에서 임의의 html파일을 생성하고 웹 브라우저를 불러온 뒤 그림과 같이 콘솔창을 띄운다.
  ![첨부1](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0313_1.png?raw=true)
  <br>
  그 다음 콘솔창에 `alert() 함수`를 이용해 자신의 이름을 출력해보자.<br>
  <br>

> **alert()함수** <br>
> alert문은 알림창을 표시한다. 그리고 이 함수의 소괄호 안에 메시지나 변수를 넣으면 알림창에 텍스트나 변숫값이 뜬다.<br>
> <span style="color:green">이때 소괄호 안에 큰 따옴표나 작은 따옴표와 함께 작성해줘야한다.</span><br>

  <br>
  <br>
  이름을 출력해야하므로 소괄호 안에 자신의 이름을 넣어준다.<br>
  <br>
  ![첨부2](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0313_2.png?raw=true)
  <br>
  <br>
  그리고 `Enter`키를 눌러주면 화면처럼 알림창에 텍스트가 뜬다.<br>
  ![첨부3](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0313_3.png?raw=true)
  <br>
  <br>
  

## 문제2
___
다음의 코드를 실행하여 나오는 '확인 창'에서 [확인] 버튼을 클릭했을 때 반환되는 값은 무엇인가?<br>
```js

confirm('프로그램을 종료하시겠습니까?');

```
<br>
<br>
  
## 문제 풀이2
  ___
  ![첨부4](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0313_4.png?raw=true)
  <br>
  <br>
  사진처럼 `true`가 나온다.<br>
  추가로 `취소`를 누를 경우, `false`가 나온다.<br>
  <br>
  
## 문제3
___
콘솔 창에 '자바스크립트를 좋아합니다'라고 출력하는 코드를 작성해 보시오.<br>
<br>
<br>

## 문제 풀이3
  ___
  콘솔창에 출력하는 문제는 `console.log() 명령을 사용해서 하면 된다.
  <br>
  <br>

> **console.log()함수** <br>
> 간단하게 텍스트로 보여주는 명령<br>
> 중간중간 프로그램이 제대로 동작하는 지 확인하는 용도<br>
> <span style="color:green">이때 소괄호 안에 큰 따옴표와 함께 작성해줘야한다.</span><br>
  <br>
  <br>

문제에서 요구한 대로 콘솔 창에 메시지를 출력해야하므로 소괄호 안에 텍스트를 넣어준다.<br>
코드를 작성한 뒤, `Enter` 키를 눌러주면 사진과 같이 결과값이 창이 아닌 콘솔창에 뜬다.<br>
<br>
![첨부5](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0313_5.png?raw=true)
<br>
<br>

## 문제4
___
변수 name을 선언해서 자신의 이름을 할당하고, 콘솔 창에 '나는 OOO입니다.'라고 출력하는 코드를 작성하시오.<br>
<br>

## 문제 풀이4
  ___
  문제3번과 같이 `console.log()`함수를 이용해서 하면 된다.
  <br>
  console.log는 뱐수와 함께 내용을 연결하여 표시도 가능하다.
  <br>
  <br>
  문제에선 변수를 `name`으로 선언하라고 지시했기 때문에 name으로 선언해준다.
```js
name = "최유이" /*자신의 이름을 할당함*/
```
<br>
<span style="color: #2D3748; background-color:#fff5b1;">코드를 보면 `C`와 `Java`와는 다르게 변수에 타입을 지정하지 않아도 된다.</span><br>
변수을 선언했고 값도 할당했으므로 다음으로 콘솔창에 해당 텍스트가 출력되도록 코드를 넣어준다.<br>
```js
name = "최유이"
console.log("나는" + name + "입니다.")
```
<br>
조합하는 것은 쉽다. 규칙대로 텍스트는 큰따옴표로 감싸주고 `ooo`자리에 변수인 name을 넣어주면 된다.<br>
![첨부6](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0313_6.png?raw=true)
<br>

## 문제5
___
 number 변수값에 100을 더한 후 result 변수에 할당하는 코드를 작성하시오.<br>

## 문제 풀이5
  ___
  변수를 선언하기 전에 let 과 const에 대해 간단하게 알아보도록 하자.<br>

> **변수 선언과 값 할당(let,const)** <br>
> <span style="color:red">`변수`</span>라면 `let`: 변수에 재할당 가능<br>
> <span style="color:blue">`상수`</span>라면 `const`: 변수 재선언/재할당 불가능<br>
  <br>
  <br>
  
  ```js
let result = number + 100; 
```
<br>

## 문제6
___
 prompt 문을 사용해 사용자 이름을 입력 받은 후 userName 변수에 저장하고, <br>
 템플릿 리터럴을 사용해 'OOO님, 반갑습니다!' 라고 콘솔창에 출력하는 코드를 작성하시오.<br>
 여기서 OOO에는 앞서 입력받은 사용자 이름이 들어가야 한다.<br>

## 문제 풀이6
  ___
  이번 문제는 prompt문을 이용한 문제이다. 문제를 풀기 앞서 prompt()함수에 대해 알아보자.<br>
  > **prompt()함수** <br>
  >> 기본형1) prompt("내용")<br>
>  > 기본형2) prompt("내용","기본값")<br>
  > 프로그램 실행에 필요한 간단한 값을 입력 받을 때 자주 사용.<br>
  > <span style="color:green">프롬프트 창을 만들 때 기본값을 지정하지 않으면 빈 텍스트 필드로 표시된다</span><br>
<br>
<br>
1. prompt 문을 사용해 사용자 이름을 입력 받기<br>
```js
prompt("사용자 이름을 입력하세요.")
```
<br>

2.입력 받은 후 userName 변수에 저장하기<br>
```js
let userName = prompt("사용자 이름을 입력하세요.")
```
prompt을 이용해 입력값을 받았으므로 이 입력값을 다시 userName에 넣어주는 코드를 작성하면 된다.<br>
<br>

3.템플릿 리터럴을 사용해 'OOO님, 반갑습니다!' 라고 콘솔창에 출력하는 코드를 작성하시오.<br>
```js
console.log(userName + "님, 반갑습니다!")
```
콘솔창에 출력하면 되므로 `console.log`를 이용해주면 된다.

## 문제7
___
'바나나', '사과', '포도'라는 값이 들어 있는 fruits 라는 배열을 선언하고,<br>
배열에서 두 번째 값을 콘솔 창에 출력하는 코드를 작성하시오.<br>

## 문제 풀이7
  ___
  이번 문제는 배열 문제로 문제를 풀기 전에 한번 배열에 대해 빠르게 짚고 넘어가도록 하자<br>

> **배열** <br>
>> 기본형) 배열명 =[값,값,값,..]<br>
> 하나의 변수에 여러 개의 값을 저장할 수 있는 `객체`<br> 
> <span style="color:blue">쉼표로 값을 구분</span><br>
  <br>
  <br>
1. '바나나', '사과', '포도'라는 값이 들어 있는 fruits 라는 배열을 선언하기<br>
```js
fruit = ["바나나","사과","포도"]
```
<br>

2.배열에서 두 번째 값을 콘솔 창에 출력하는 코드를 작성하기<br>
```js
fruit[1]
```
<br>

## 문제8
___
name, age, gender라는 키를 가지고 있는 person이라는 객체를 만드는 코드를 작성하시오.<br>
각 키의 값에는 자신에 해당하는 값을 넣으시오.<br>

## 문제 풀이8
  ___
  이번 문제는 자바 객체 문제라고 보면 된다.<br>
  그러므로 바로 코드 짜기로 들어가보면<br>

```js
let person = {
  name : "최유이",
  age : 20,
  gender : "F"
}
```
<br>

~~20살은 아니지만 되고 싶어서 그냥 20살로 적어봤다 시간이 정말 빠르다..~~ <br>

## 문제9
___
화씨 온도를 섭씨 온도로 변환하기 실습을 따라해서 결과 화면을 첨부하시오.<br>

## 문제 풀이9
  ___
  9번 문제는 실습에 따라서 하는 문제이므로 사진으로 대체한다.<br>
![첨부7](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0313_7.png?raw=true)
<br>
![첨부8](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0313_8.png?raw=true)
<br>

## 문제10
___
다음 표현식의 결과를 쓰시오.<br>
![첨부9](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0313_9.png?raw=true)
<br>
<br>

## 문제 풀이10
  ___
  10번 문제는 표에 빈칸 넣는 문제이며 해설 칸이 있으므로 사진으로 대체한다.<br>

| 표현식               | 결과           | 해설
|:---------------------|:---------------|:----------------------------------------------
| 4 + 10               | 14             | 숫자+숫자=숫자
| 4 + "10"             | "410"          | 숫자+문자=(통합하고)문자
| ParseInt(10+0.5)     | 10             | 숫자끼리 계산 뒤, 소수점을 제외한 10만 살아남음 
| "10" + 0.5           | "100.5"        | 문자+숫자=(통합하고)문자
| 10 + 0.5             | 10.5           | 숫자+숫자=숫자
| ParseFloat("10"+0.5) | 100.5          | 숫자끼리 계산 뒤, `Float`이므로 소수점까지 살림



## 문제11
___
사용자로부터 인치를 입력받아 센티미터로 바꾸는 프로그램을 작성하시오. 1인치는 2.54cm이다<br>
<br>

## 문제 풀이11
  ___
  이 문제는 9번 문제와 유사한 문제로 바로 코드작성으로 들어가보자.<br>
  <br>
  먼저 임의의 새로운 `html` 파일을 생성한 뒤, body부분에 제목을 넣어보자<br>
  제목은 "인치를 입력받아 센티미터로 변환하기" 로 해뒀다. 내용 부분은 제목과 동일하게 하고 크기를 `h1`으로 설정함.<br>
  
```js
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>인치를 입력받아 센티미터로 변환하기</title>
</head>
<body>
  <h1>인치를 입력받아 센티미터로 변환하기</h1>
  <script src="js/convert-result.js"></script>
</body>
</html>
```

```js
let inch = parseFloat(prompt("변환할 인치"));
let cm;

cm = (inch*2.54).toFixed(2);
alert(`${inch} inch는 ${cm} cm입니다.`);
```

