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
**1.["봄", "여름", "가을", "겨울"] 배열에서 세 번째, 네 번째 요소를 각각 fall과 winter라는 변수에 할당하기.** 
<br>
<br>
<br>
✔️

```js
let [ , , fall,winter] = ["봄","여름","가을","겨울"]
```
<br>
<br>

## 문제2 && 문제 풀이2
___
**2.[실습] 개설 요청 과목 정리하기** 
<br>
<br>
<br>
✔️

```js
const member1 = ["HTML", "CSS"];
const member2 = ["CSS", "자바스크립트", "리액트"];
const member3 = ["자바스크립트", "타입스크립트"];

const subjects = [...member1, ...member2, ...member3];
// console.log(subjects);

const resultList = new Set();
subjects.forEach(subject => {
  resultList.add(subject);
});
// console.log(resultList);

const result = document.querySelector("#result");
result.innerHTML = `
  <ul>
  ${[...resultList]
  .map(subject => `<li>${subject}</li>`)
  .join("")}
  </ul>
`;
```
<br>
<br>

## 문제3 && 문제 풀이3
___
**3.자바스크립트를 사용해서 자동으로 복권 번호를 생성해 주는 프로그램을 작성하려 합니다.** <br>
**번호는 증복되면 안되므로 셋을 이용할 것이고, 숫자는 1부터 45까지의 범위 안에 있어야 하며,** <br>
**6개의 무작위 수를 추출할 것입니다. 버튼을 클릭했을 때** <br>
**모든 조건을 반영해서 6개의 숫자를 추출하는 소스를 작성해 보세요.**
<br>
<br>
<br>
✔️
<br>
<br>
