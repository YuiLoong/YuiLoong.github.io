---
categories: Java
toc: true
---

## 자바스크립트 9장 객체 문제(1) 
* this list will be replaced by the table of contents
{:toc .large-only}
  <br> 
  <br>
  <br>
  <br>
 

## 문제1 && 문제 풀이1
___
**1. book1 객체에 책을 읽는 중인지 알려주는 done이라는 프로퍼티를 추가하시오.값은 true나 false 중에 선택하면 된다.** <br>
<br>
<br>

✔️
<br>

**[코드]** <br>

```js
book1.done = true 혹은 book1["done"] = true
```
<br> 
<br>

## 문제2 && 문제 풀이2
___
**2. [실습] 생성자 함수와 클래스를 사용해 원기둥 부피 구하기** <br>
<br>
<br>

✔️
<br>

**[코드]** <br>

```js
class Cylinder {
  constructor(cylinderDiameter, cylinderHeight) {
    this.diameter = cylinderDiameter;
    this.height = cylinderHeight;
  }
  volume() {
    let radius = this.diameter / 2; // 반지름 계산하기
    return (Math.PI * radius * radius * this.height).toFixed(2); // 부피 계산해서 반환
  }
}

// let cylinder = new Cylinder(8, 10);      // 인스턴스 생성
// console.log(`원기둥의 부피는 ${cylinder.volume()}입니다.`);     // 결괏값 표시

const button = document.querySelector("button"); // [계산하기] 버튼
const result = document.querySelector("#result"); // 결괏값 표시 영역

button.addEventListener("click", function (event) {
  event.preventDefault();
  const diameter = document.querySelector("#cyl-diameter").value; // 지름값
  const height = document.querySelector("#cyl-height").value; // 높잇값

  if (diameter === "" || height === "") {
    result.innerText = `지름값과 높잇값을 입력하세요.`;
  } else {
    let cylinder = new Cylinder(parseInt(diameter), parseInt(height)); // 인스턴스 생성
    result.innerText = `원기둥의 부피는 ${cylinder.volume()}입니다.`; // 부피 계산해서 result 영역에 표시
  }
});
```

<br>

**[결과창]** <br>

![첨부1](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0409_6.png?raw=true)
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
**4. 08\js\circle.js에서 결괏값을 반올림하는 소스로 수정해 보세요.** <br>
<br>
<br>

✔️
<br>

**[코드]** <br>

```js
// 반올림
result.innerText = `
    반지름 : ${radius},
    원의 넓이 : ${Math.round(area(radius))},
    원의 둘레 : ${Math.round(circum(radius).toFixed(3))}
  `;
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
