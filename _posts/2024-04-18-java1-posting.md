---
categories: Java
toc: true
---

## 자바스크립트 문자열과 배열 활용하기 문제(2)
* this list will be replaced by the table of contents
{:toc .large-only}
  <br> 
  <br>
  <br>
  <br>

## 문제1 && 문제 풀이1
___
**1.다음 배열에 대한 설명 중 틀린 것은?** 
<br>

```js
let months = new Array("Jan", "Feb", "March");
```
<br>
① let months = ["Jan", "Feb", "March"]; 로 대신할 수 있다.
<br>
② months.length는 3이다.
<br>
③ months[1] = "Februray"; 코드는 "Feb"를 "Februray"로 수정한다.
<br>
④ months.length = 5로 지정하여 배열의 크기를 5개로 늘릴 수 없다.
<br>
<br>
<br>
✔️

<span style="color: red;">④ months.length = 5로 지정하여 배열의 크기를 5개로 늘릴 수 없다.</span>
<br>
❖ 길이를 변경할 수 있다.
<br>
<br>

## 문제2 && 문제 풀이2
___
**2.다음 배열에 대한 설명 중 틀린 것은?**
<br>
```js
let grades = new Array("A", "B", "C", "D");
```
<br>
① grades[4] = "F";를 실행하면 grades 배열의 크기가 1 늘어난다.
<br>
② grades[3] = 70;은 잘못된 코드이다. 왜냐면 문자열 배열에 정수를 넣었기 때문.
<br>
③ grades.reverse()를 호출한 결과 grades 배열 내부가 ["D", "C", "B", "A"]로 변한다.
<br>
④ grades.length는 4이다.
<br>
<br>
<br>

  ✔️ 
  <br>
<span style="color: red;">② grades[3] = 70;은 잘못된 코드이다. 왜냐면 문자열 배열에 정수를 넣었기 때문.</span>
<br>
❖ 타입형이 없기 때문에 딱히 잘못된 코드는 아니다.
<br>
<br>
<br>

## 문제3 && 문제 풀이3
___
**3.주석에 맞게 다음 빈 칸을 채우시오.** <br>
```js
let ______________________________               // Array를 이용하여 크기가 3인 배열 money 생성
_____________________________ = 5;               // money의 첫 번째 요소에 5 삽입
_____________________________ = 7;               // money의 두 번째 요소에 7 삽입
_____________________________ = -3;              // money의 세 번째 요소에 -3 삽입
let sum = 0;
for (let i=0; i<_______________; i++) sum += money[i];     // 배열 합 구하기
document.write(________________);                // 평균 출력
```
<br>
<br>
<br>

  ✔️ <br>
  
```js
let money = new Array(3);
money[0] = 5;
money[1] = 7;
money[2] = -3;
let sum = 0;
for(let i=0; i<money.length;i++) sum+= money[i];
document.write(sum/3);
```
<br>
<br>
<br>
  
## 문제4 && 문제 풀이4
___
**4. 다음 코드를 실행하면 출력될 변수 result의 값을 고르세요.** <br>

```js
const result = (function(a, b){
  function init(){
    return doSum(a, b);
  }
  function doSum(a, b){
    return a + b;
  }
  return init();
})(10, 20);
console.log(result);
```
<br>
① undefined
<br>
② null
<br>
③ 50
<br>
④ 30
<br>
⑤ SyntaxError
<br>
<br>
✔️ 
<br>
① undefined
<br>
② null
<br>
③ 50
<br>
<span style="color: red;">④ 30</span>
<br>
❖ a=10, b=20 값이 들어가서 dosum()함수 실행.
<br>
<br>
⑤ SyntaxError
<br>
<br>

## 문제5 && 문제 풀이5
___
**5. 원의 넓이를 구하는 공식은 (반지름) × (반지름) × (원주율)입니다.** <br>
**원주율은 3.14라고 했을 때, 원의 반지름을 이용해 원의 넓이를 반환하는 함수를 만들어 보세요.**
<br>
*(콘솔 출력) 반지름 ○인 원의 넓이는 □ □ □입니다.)*
<br>
<br>
<br>
  ✔️ <br>
  
```js
function Circle(radius) {
    const pi = 3.14;
    const s = pi * radius * radius;
    return s;
}

const radius = prompt("반지름 입력하세요"); // 반지름
const s = Circle(radius); // 함수 호출을 통해 원의 넓이 계산
console.log(`반지름 ${radius}인 원의 넓이는 ${s}입니다.`);

```
<br>

![첨부1](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0323_1.png?raw=true)
<br>
<br>

## 문제6 && 문제 풀이6
___
**6. 매개변수로 배열을 전달받아 배열의 요소 중에서 가장 큰 수를 찾아 반환하는 함수를 만들어 보세요.** <br>
**이때, 배열 안의 데이터는 모두 0보다 큰 정수라고 가정합니다.** <br>
>*테스트 배열: [10, 20, 50, 5, 30]* <br>
>*콘솔 출력) 가장 큰 수는 50입니다.*
<br>
<br>
<br>

  ✔️ <br>

```js
function Number(arr) {
    let max = arr[0]; 
    
    for (let i = 0; i < arr.length; i++) {
        if (arr[i] > max) {
            max = arr[i]; 
        }
    }
    return max; // 최대값 반환
}

const testArray = [10, 20, 50, 5, 30];
const MaxNumber = Number(testArray);
console.log(`가장 큰 수는 ${MaxNumber}입니다.`);

```
<br>

![첨부5](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0323_2.png?raw=true)
<br>
<br>

## 문제7 && 문제 풀이7
___
**7.체질량 지수(BMI)를 계산하는 공식은 몸무게를 키(m)의 제곱으로 나눈 값입니다.** <br>
**사용자에게 키(cm)와 몸무게(kg)에 해당하는 값을 전달받아 체질량 지수를 계산합니다.** <br>
**체질량 지수가 26점 이상이면 비만, 24-25점은 과체중, 18.5-23점은 정상, 18.5점 미만은 저체중을 반환하는 함수를 만들어 보세요.**
<br>
>테스트 #1) 키: 180cm, 몸무게: 100kg → 콘솔출력: 비만 <br>
>테스트 #2) 키: 180cm, 몸무게:   80kg → 콘솔출력: 과체중 <br>
>테스트 #3) 키: 180cm, 몸무게:   70kg →콘솔 출력: 정상 <br>
>테스트 #4) 키: 180cm, 몸무게:   59kg → 콘솔출력: 저체중 <br>

<br>
<br>

  ✔️ <br>

```js
function BMI(height, weight) {
    const heightMeter = height / 100; // cm -> m으로 변환
    const bmi = weight / (heightMeter * heightMeter); // bmi 공식

    if (bmi >= 26) {
        return "비만";
    } else if (bmi >= 24 && bmi <= 25) {
        return "과체중";
    } else if (bmi >= 18.5 && bmi <= 23) {
        return "정상";
    } else {
        return "저체중";
    }
}

// 입력 받고 값 출력
let height = prompt("키 입력하세요");
let weight = prompt("몸무게 입력하세요");
console.log(`키: ${height}cm, 몸무게: ${height}kg 은 ${BMI(height, weight)}`);

```
<br>

![첨부5](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0323_3.png?raw=true)
<br>
<br>
