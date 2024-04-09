---
categories: Java
toc: true
---

## 자바스크립트 8장 내장 객체 문제(1) 
* this list will be replaced by the table of contents
{:toc .large-only}
  <br> 
  <br>
  <br>
  <br>
 

## 문제1 && 문제 풀이1
___
**1.자신의 생일을 사용해 Date 인스턴스를 만들고 birthDay라는 변수로 설정해 보세요.** <br>
<br>
<br>
<br>




<br>
<br>
✔️
<br>

**[코드]** <br>
```js
 let birthDay = new Date("0000-08-07")
```
<br>

**[결과창]** <br> 

<br>

## 문제2 && 문제 풀이2
___
**2.행(row)과 열(column)의 개수를 입력한 값에 따라 힌트를 참고하여 표를 그리는 소스를 작성하세요.** <br>
**표를 구성하는 table, td, tr 요소의 관계를 잘 생각하고 노드를 추가하여 작성하세요.** <br>
**여기에서는 작성한 소스가 완벽하지 않더라도 DOM을 사용해 표를 그리는 것에 집중해 만들어 보세요.** <br>

*힌트*

1) table 요소 노드를 만듭니다.<br>

2) 입력한 행의 개수만큼 반복하면서 tr 요소노드를 만듭니다.<br>

3) 입력한 열의 개수만큼 다음 과정을 반복합니다.<br>

    (1) td 요소노드를 만듭니다.<br>

    (2) 텍스트 노드를 만듭니다.<br>

    (3) 텍스트 노드를 td 요소 노드의 자식 노드로 만듭니다. <br>

    (4) td 요소를 tr 노드의 자식 노드로 만듭니다. <br>
<br>

4) tr 요소 노드를 table 요소 노드의 자식 노드로 만듭니다.
<br>
5) table 요소 노드를 필요한 위치에 추가합니다.
<br>
<br>
<br>
✔️

<br>

**[코드]** <br>

```js
 <script>
let bttn = document.querySelector("#bttn");
bttn.addEventListener("click", function (event) {
    event.preventDefault(); // 기본 이벤트 방지
    let table = document.createElement("table");

    // 입력한 행 개수만큼 반복
    for (let i = 0; i < rCount.value; i++) {
        // tr 요소노드 만들기
        let tr = document.createElement("tr");
    

         // 입력한 열 개수만큼 반복
         for (let j = 0; j < cCount.value; j++) {
                // td 요소노드 만들기
                let td = document.createElement("td");
                // 텍스트 요소노드 
                let text = document.createTextNode("가나다");
                // 텍스트 노드를 td 자식으로 추가
                td.appendChild(text);
                // td 행의 자식으로 추가
                tr.appendChild(td);
            }

            // tr 요소 노드를 table 요소 노드의 자식 노드
            table.appendChild(tr);

        var contents = document.querySelector("#contents");
        contents.innerHTML = ""; // contents 요소 초기화
        contents.appendChild(table);
        }        
    });

  </script>
```
<br>

**[결과창]** <br>

![첨부3](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0404_3.png?raw=true)
<br>
<br>
