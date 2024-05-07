---
categories: Java
toc: true
---

## 스프링부트 2장 실습(1)
* this list will be replaced by the table of contents
{:toc .large-only}
  <br> 
  <br>
  <br>
  <br>

## 문제1 && 문제 풀이1
___
**1. 다음 ㉠~㉤에 들어갈 알맞은 용어를 찾아 쓰세요.**
<br>
<br>

( ㉠ )(이)란 웹 페이지를 일종의 틀로 만든 것이다.
<br>
( ㉡ )은/는 클라이언트의 요청을 받아 서버에서 이를 처리하는 역할을 한다.
<br>
( ㉢ )은/는 뷰 템플릿에서 사용되는 데이터를 관리하는 역할을 한다.
<br>
( ㉣ )은/는 이 클래스가 컨트롤러임을 선언한다.
<br>
( ㉤ )은/는 클라이언트의 URL 요청을 받아 특정 컨트롤러의 메서드가 처리하게 한다.
<br>
<br>
① @Controller
<br>
② 컨트롤러
<br>
③ @GetMapping
<br>
④ 뷰 템플릿
<br>
⑤ 모델
<br>
<br>
<br>

✔️
<br>

**답**
<br>
ㄱ) 4번
<br>
ㄴ) 2번
<br>
ㄷ) 5번
<br>
ㄹ) 1번
<br>
ㅁ) 3번
<br>
<br>
<br>

## 문제2 && 문제 풀이2
___
**2. 다음 설명 중 옳지 않은 것을 고르세요.**
<br>

① 웹 브라우저는 서버로 URL 요청을 보내 결과 뷰 템플릿 페이지를 반환받는다.
<br>
② 컨트롤러의 메서드는 URL 요청을 받아 처리한 후 결과 뷰 템플릿 페이지를 반환한다.
<br>
③ 컨트롤러의 메서드 반환값은 뷰 템플릿 페이지의 확장자를 포함해 작성한다.
<br>
④ 뷰 템플릿 페이지에서 변수를 사용하려면 모델에 변수가 등록돼 있어야 한다.

<br>
<br>
<br>
✔️
<br>

**답**

<br>
<br>

## 문제3 && 문제 풀이3
___
**3. 다음 ㉠~㉢에 들어갈 알맞은 용어를 쓰세요.**

<br>
<br>

( ㉠ )(이)란 화면에 요소를 배치하는 것을 말한다. 웹 페이지는 같은 요소로도 어떻게 배치하느냐에 따라 다른 느낌을 줄 수 있다.
<br>
( ㉡ )(이)란 웹 페이지를 쉽게 만들 수 있도록 작성해 놓은 코드 모음으로 미리 작성된 HTML/CSS/자바스크립트 코드를 가져다 사용할 수 있다.
<br>
( ㉢ )(이)란 코드를 하나의 틀로 만들어 변수화하는 것을 말한다.
<br>
<br>
<br>
✔️
<br>

## 문제4 && 문제 풀이4
___
**4. 다음과 같이 랜덤으로 명언이 나오는 페이지를 만들려고 한다.**

<br>
<br>

![첨부1](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0507_1.png?raw=true)

<br>

*사용할 뷰 템플릿 파일(quote.mustache)은 다음과 같다.*
<br>
<br>
![첨부2](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0507_2.png?raw=true)
<br>
![첨부3](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0507_3.png?raw=true)
<br>
✔️

