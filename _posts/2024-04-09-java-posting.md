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
**1. 자신의 생일을 사용해 Date 인스턴스를 만들고 birthDay라는 변수로 설정해 보세요.** <br>
<br>
<br>

✔️
<br>

**[코드]** <br>
```js
let birthDay = new Date("0000-08-07")
```
<br> 
<br>

## 문제2 && 문제 풀이2
___
**2. 만 보 걷기, 오늘까지 며칠째일까?** <br>
<br>
<br>

✔️
<br>

**[코드]** <br>

```js
const firstDay = new Date("2024-01-01");
const today = new Date();

let diff = (today.getTime()-firstDay.getTime()) / (24*60*60*1000);
document.querySelector("#result").innerHTML = Math.round(diff);
```
<br>

**[결과창]** <br>

![첨부1](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0409_1.png?raw=true)
<br>
<br>

## 문제3 && 문제 풀이3
___
**3. 디지털 시계 만들기** <br>
<br>
<br>

✔️
<br>

**[코드]** <br>

```js
<script>
    function display() {

      const today = new Date(); //현재 날짜
      const displayDate = document.querySelector("#today");
      const displayTime = document.querySelector("#clock");

      let day = ""; //요일
      switch(today.getDay()){
        case 0:
          day = "일";break;
        case 1:
          day = "월";break;
        case 2:
          day = "화";break;
        case 3:
          day = "수";break;
        case 4:
          day = "목";break;
        case 5:
          day = "금";break;
        case 6:
          day = "토";break;

      }
    
      let text = `${today.getFullYear()}년 ${today.getMonth()+1}월 ${today.getDate()}일 ${day}요일`;
      displayDate.innerHTML = text; //날짜 찍기

      let h = today.getHours(); //시간
      const ampm = (h < 12) ? "AM" : "PM";
      h = (h > 12) ? h -12 : h; //13시 이후 처리 
      h = (h == 0)? 12 : h; //시간이 두자리 수, 한자리 수처리

      const hStr = (h < 10 ) ? "0"+h: ""+h;
      let min = today.getMinutes();
      const minstr = (min < 10)? "0"+min : ""+min;
      let sec = today.getSeconds();
      const secstr = (sec < 10)? "0"+sec : ""+sec;

      text = `${ampm} ${hStr}시 ${minstr} 분 ${secstr} 초`;
      displayTime.innerHTML = text;
    }
    setInterval(display,1000);
    
   
  </script>
```
<br>

**[결과창]** <br>

![첨부2](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0409_2.png?raw=true)
<br>
<br>


## 문제5 && 문제 풀이5
___
**5. 웹 문서의 배경 이미지 무작위로 변경하기** <br>
<br>
<br>

✔️
<br>

**[코드]** <br>

```js
<script>
    const h1 = document.querySelector("h1");
    const body = document.querySelector("body");

    h1.addEventListener("click", function(){
      const sel = Math.floor(Math.random()*5 +1);
      body.style.backgroundImage = `url('images/bg-${sel}.jpg')`;  
    });
</script>
```
<br>

**[결과창]** <br>

![첨부3](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0409_3.png?raw=true)
<br>
<br>
