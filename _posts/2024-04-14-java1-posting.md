---
categories: Java
toc: true
---

## 자바스크립트 9장 객체 문제(2) 
* this list will be replaced by the table of contents
{:toc .large-only}
  <br> 
  <br>
  <br>
  <br>
 

## 문제1 && 문제 풀이1
___
**1. 다음 코드를 실행한 후 마지막에 변수 studentObject에 할당된 객체의 키를 배열로 나열한 값을 고르세요.** <br>

```js
const studentObj = {
  name: "John",
  age: age,
};
studentObj.gender = "female";
delete studentObj.age;
```
<br>
<br>
<br>

✔️
<br>
답: 3) ['name', 'gender']
<br>
해설: age가 삭제 되었고 gender 키가 추가되었으므로 3번이다.
<br> 
<br>

## 문제2 && 문제 풀이2
___
**2. 2. 다음 중 obj 변수에 할당된 객체의 속성과 값이 다른 하나를 고르세요.** <br>
2. 다음 중 obj 변수에 할당된 객체의 속성과 값이 다른 하나를 고르세요.

➀  const obj = {name: "철수"}; <br>

➁ const obj = {}; 
 <br>
    obj.name = "철수";
<br>

➂ const obj = {name: "철수", age: 20};
<br>
    delete obj.name;
<br>

➃ const obj = {name: "영희"};
<br>
    obj.name = "철수";
<br>

➄ const obj = {};
<br>
    const obj2 = obj;
<br>
    obj2.name = "철수";
<br>
<br>

✔️
<br>

답: 3번
<br>
해설: 나머지는 {name:철수}지만, 3번은 name 속성이 삭제 되었으므로 age 키,값이 나온다.
<br>
<br>

## 문제3 && 문제 풀이3
___
**3. 자바스크립트에서 객체를 생성하는 키워드로 알맞은 것은?** <br>

➀  instance      ➁ object      ➂ new      ➃ create

<br>
<br>
<br>

✔️
<br>

답: 3번 new가 알맞다.
<br>
<br>
<br>

## 문제4 && 문제 풀이4
___
**​4. 자바스크립트에서 키워드 this가 의미하는 것은?** <br>

➀  현재 스크립트     ➁ 현재 문서      ➂ 현재 객체      ➃ 현재 브라우저
<br>
<br>
<br>

✔️
<br>

답: 3번 
<br>
해설: this는 해당 메서드를 호출한 현재 객체를 가리키므로
<br>
<br>
<br>



## 문제5 && 문제 풀이5
___
**5. 객체 dog에 color라는 속성을 저장하고자 한다. 올바르게 저장하는 문장은?** <br>

➀  dog.color = 'orange';     ➁ dog[color] = 'orange';     ➂ dog_color = 'orange';     ➃ let dog.color = 'orange';
<br>
<br>
<br>

✔️
<br>
답: 1
<br>
해설: dog 객체에 color라는 속성에 orange 값을 할당하는 문장은 1번이 올바르다.
<br>
<br>

## 문제6 && 문제 풀이6
___
**6. 사용자를 나타내는 객체를 생성하고자 한다. 객체는 아이디, 나이, 패스워드 속성을 가지고 있다.** <br>
**{kim, 20, 1234} 값을 이용해 객체 하나를 생성한 후 객체의 모든 속성을 웹 페이지에 출력하는 코드를 작성하시오.** <br>
<br>
<br>

✔️
<br>

**[코드]** <br>

```js
const user = {
    id: "kim",
    age: 20,
    password: "1234"
};
```
<br>

**[결과창]** <br>

![첨부2](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0411_2.png?raw=true)
<br>
<br>
<br>
