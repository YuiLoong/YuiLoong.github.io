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
**3. [실습] 프로토타입을 상속하는 새로운 객체 만들기** <br>
<br>
<br>

✔️
<br>

**[코드]** <br>

```js
function Book (title, price) {
  this.title = title;
  this.price = price;
}

Book.prototype.buy = function() {
  console.log(`${this.title}을(를) ${this.price}원에 구매하였습니다.`);  
}

const book1 = new Book("ABCDE", 10000);   
book1.buy();  // Book 객체의 buy() 메서드 사용

// 기존 객체를 확장해서 새로운 객체 만들기
function Textbook(title, price, major) {
  Book.call(this, title, price);   // 기존 객체의 프로퍼티 재사용
  this.major = major;               // 새로운 프로퍼티 정의
}

Textbook.prototype.buyTextbook = function() {   // 새로운 메서드 정의
  console.log(`${this.major} 전공 서적, ${this.title}을 구매했습니다.`);
}

Object.setPrototypeOf(Textbook.prototype, Book.prototype);   // Textbook 프로토타입을 Book 프로토타입으로 연결

const book2 = new Textbook("알고리즘", 5000, "컴퓨터공학");
book2.buyTextbook();     // Textbook 객체의 메서드 사용
book2.buy();             // Book 객체의 메서드 사용

```
<br>
<br>
<br>

## 문제4 && 문제 풀이4
___
**4.[실습] 클래스 상속 연습하기** <br>
<br>
<br>

✔️
<br>

**[코드]** <br>

```js
class BookC  {
  constructor(title, price) {
    this.title = title;
    this.price = price; 
  }
  buy() {
    console.log(`${this.title}을(를) ${this.price}원에 구매하였습니다.`);  
  }
}

const book1 = new BookC("자료 구조", 15000);
book1.buy();

// 기존 클래스를 확장해서 새로운 클래스 선언하기
class TextbookC extends BookC {
  constructor(title, price, major) {
    super(title, price);   // 기존 클래스의 프로퍼티 재사용
    this.major = major;     // 새로운 프로퍼티 정의
  }

  buyTextbook () {   // 새로운 메서드 정의
    console.log(`${this.major} 전공 서적, ${this.title}을 구매했습니다.`);
  }
}

const book2 = new TextbookC("인공지능", 5000, "컴퓨터공학");
book2.buyTextbook();
book2.buy();
```
<br>
<br>
<br>



## 문제5 && 문제 풀이5
___
**5. Pet 클래스를 만든 후 인스턴스 객체를 만들어 보세요. 이때 Pet 클래스는 name과 color 프로퍼티, run() 메서드를 가지고 있습니다.** <br>
**그리고 run() 메서드는 반려동물의 이름과 함께 'is running.'이라는 문자열을 알림 창에 표시하도록 정의합니다.** <br>
<br>
<br>

✔️
<br>

**[코드]** <br>

```js
<script>
  class Pet{
    constructor(name,color){
      this.name = name;
      this.color = color;
    }
    run() {
      alert(`${this.name} is running`);
    }
  }

  let myPet = new Pet("온유","초록색");
  myPet.run();
</script>
```
<br>

**[결과창]** <br>

![첨부1](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0411_1.png?raw=true)
<br>
<br>

## 문제6 && 문제 풀이6
___
**6. 5번에서 만들었던 Pet 클래스를 상속받는 Cat 클래스를 만들어 보세요.** <br>
**이때 Cat 클래스에는 고양이 품종을 나타내는 breed라는 프로퍼티를 추가하고 객체의 이름과 색상, 품종을 표시하는 viewInfo() 메서드도 추가합니다.** <br>
**그리고 Cat 클래스의 인스턴스를 만들고 인스턴스 객체에서 viewInfo() 메서드를 실행해 보세요.** <br>
<br>
<br>

✔️
<br>

**[코드]** <br>

```js
 <script>
  class Pet{
    constructor(name,color){
      this.name = name;
      this.color = color;
    }
    run() {
      alert(`${this.name} is running`);
    }
  }

  // let myPet = new Pet("온유","초록색");
  // myPet.run();

  class Cat extends Pet{
      constructor(name, color, bread){
        super(name, color);
        this.breed = bread;
      }
      viewInfo() {
        alert(`이름: ${this.name}, 품종: ${this.breed}, 색상: ${this.color}`);
      }
    }
    let myCat = new Cat("고양이","삼색","삼색고양이");
    myCat.viewInfo();
</script>
```
<br>

**[결과창]** <br>

![첨부2](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0411_2.png?raw=true)
<br>
<br>
<br>
