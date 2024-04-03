---
categories: Java
toc: true
---

## 자바스크립트 7장 DOM 활용하기 문제(1) 
* this list will be replaced by the table of contents
{:toc .large-only}
  <br> 
  <br>
  <br>
  <br>
 

## 문제1 && 문제 풀이1
___
**1. 장바구니에 상품 추가하기 실습** <br>
<br>
<br>
✔️
<br>
**[코드]** <br>


```js
 <script>
    const orderButton = document.querySelector("#order");
    const orderInfo = document.querySelector("#orderInfo");
    const title = document.querySelector("#container > h2");
    orderButton.addEventListener("click", ()=> {
      let newP = document.createElement("P");
      let textNode = document.createTextNode(title.innerText);
      newP.appendChild(textNode);
      orderInfo.appendChild(newP);
    })
  </script>
```
<br>

**[결과창]** <br> 

![첨부1](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0402_1.png?raw=true)
<br>

## 문제2 && 문제 풀이2
___
**2. 시간에 따라 다른 이미지 표시하기 실습** <br>

<br>
<br>
✔️

<br>

**[코드]** <br>

```js
 <script>
    const today = new Date();
    const hrs = today.getHours();
    let newImg = document.createElement("img");
    newImg.src = (hrs < 12)? "images/morning.jpg":"images/afternoon.jpg";
    const container = document.querySelector("#container");
    container.appendChild(newImg);

  </script>
```
<br>

**[결과창]** <br>

![첨부2](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0402_2.png?raw=true)
<br>
<br>


## 문제3 && 문제 풀이3
___
**3. 07\insert.html 문서에서 [텍스트 추가] 버튼을 클릭하면 'Javascript" 텍스트 앞에 'Typescript"를 추가하는 자바스크립트 소스 작성** <br>
<br>
<br>

  ✔️ 
  <br> 
**[코드]** <br>

  ```js
  <script>
    let button = document.querySelector("button");

    button.addEventListener("click",function(){
      let tdNode = document.createElement("p");
      let tdTextNode = document.createTextNode("Typerscript ");
      tdNode.appendChild(tdTextNode);

      let trNode = document.querySelectorAll("p")[2];
      document.body.insertBefore(tdNode,trNode);
    });
  </script>
```
<br>

**[결과창]** <br>

  
  
![첨부6](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0402_6.png?raw=true)
<br>
<br>
<br>
  
## 문제4 && 문제 풀이4
___
**4. 나만의 도서 목록 만들기 실습** <br>
<br>
<br>
✔️ 
<br>

**[코드]** <br>

```js
<script>
    const title = document.querySelector("#title");
    const author = document.querySelector("#author");
    const save = document.querySelector("#save");
    const bookList = document.querySelector("#bookList");

    save.addEventListener("click", function(e){
      e.preventDefault(); //form에 이벤트가 가는 것을 막는다.
      const item = document.createElement("li");
      item.innerHTML = `${title.value} - ${author.value}
      <span class = "delButton">삭제 </span>`;
      bookList.appendChild(item);
      title.value ="";
      author.value="";
      
      //삭제 버튼 만들기
      const delButtons = document.querySelectorAll(".delButton");
      delButtons[delButtons.length-1].addEventListener("click", function(){
        this.parentNode.remove();
      })
      // for(let delButton of delButtons){
      //   delButton.addEventListener("click", function(){
      //     this.parentNode.remove();
      //   })
      // }
    });
  </script>
```

**[결과창]** <br>


![첨부3](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0402_3.png?raw=true)
<br>
![첨부4](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0402_4.png?raw=true)
<br>
<br>

## 문제5 && 문제 풀이5
___
**5. 스터디 그룹을 만들기 위해 참가자 명단을 작성하려 한다.** <br>
**07\quiz-1.html에 필요한 양식이 미리 만들어져 있으므로 이름과 전공을 입력하면 그 값을 받아서 표에 표시하는 소스 코드를 작성하시오.**  
<br>
<br>
<br>

  ✔️ <br> 
  
**[코드]** <br>

```js
<script>
    const username = document.querySelector("#username");
    const major = document.querySelector("#major");
    const bttn = document.querySelector("#container button");
    const tbody = document.querySelector("#attendant > tbody");

    bttn.addEventListener("click",function(e) {
      e.preventDefault();
      const trNode = document.createElement("tr");
      const tdNode1 = document.createElement("td");
      const tdNode2 = document.createElement("td");

      tdNode1.innerText = username.value;
      tdNode2.innerText = major.value;
      trNode.appendChild(tdNode1);
      trNode.appendChild(tdNode2);
      tbody.appendChild(trNode);

    })

  </script>
```
<br>

**[결과창]** <br>

![첨부5](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0402_5.png?raw=true)

<br>
<br>
<br>

## 문제6 && 문제 풀이6
___
**6. [클릭] 버튼을 클릭할 때마다 화면의 오른쪽에 '알림 내용이 표시됩니다.'라는 메시지를 표시하시오.** <br>
**그리고 메시지가 계속 화면에 나타나면 불편하므로 메시지가 3초 후에 자동으로 삭제되도록** <br>

>**사용할 파일** <br>

 * 07\quiz-2.html <br>
 * 07\js\quiz-2.js (신규 작성) <br>
<br>

>**힌트** <br>

 * 알림 내용이 표시될 영역을 웹 브라우저 창의 오른쪽 위에 배치하고 여기에 새로운 요소를 연결한다.<br>
 * 버튼을 클릭하면 div 요소를 만들고 innerText를 사용해서 추가한다. <br>
 * 좀 더 보기 좋게 하기 위해 새로 만든 div 요소에 미리 만든 .noti 스타일을 추가한다. <br>
 * 미리 만든 영역에 새로 만든 div 요소를 연결한다. <br>
 * setTimeout() 메서드를 사용해서 새로 만든 div 요소가 3초 후에 삭제되도록 지정한다. <br>

<br>
<br>
✔️
<br>

**[코드]** <br>


```js
 <script>
    const box = document.querySelector("#noti-box");
    const bttn = document.querySelector("#bttn");

    bttn.addEventListener("click",function(){
      let noti = document.createElement("div");
      noti.innerText = "알림 내용이 표시됩니다.";
      box.appendChild(noti);

      setTimeout(function(){
        noti.remove();
      },3000);

    });

  </script>

```
d
<br>
<br>

**[결과창]** <br>

![첨부7](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0402_7.png?raw=true)

