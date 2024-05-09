---
categories: Java
toc: true
---

## 스프링부트 3장 실습(1)
* this list will be replaced by the table of contents
{:toc .large-only}
  <br> 
  <br>
  <br>
  <br>

## 문제1 && 문제 풀이1
___
**1. 다음 중 옳지 않은 것을 고르세요.**
<br>
<br>

① <form> 태그의 action 속성에는 데이터를 전달할 URL 주소가 담긴다.
<br>
② <form> 태그의 method 속성에는 get만 사용할 수 있다.
<br>
③ @PostMapping 어노테이션은 post 방식으로 전달된 요청을 받아 컨트롤러의 메서드에 전달한다.
<br>
④ 폼 데이터를 자동으로 받으려면 입력 폼에서 <input>, <textarea> 태그의 name 속성과 DTO 클래스의 필드명이 같아야 한다.

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
**2. 다음 ㉠~㉢에 들어갈 용어를 쓰세요.**
<br>

( ㉠ )(이)란 JPA에서 제공하는 어노테이션으로, 이를 부여받은 클래스를 기반으로 DB 속 테이블이 생성됩니다.
<br>
<br>
( ㉡ )(이)란 JPA에서 제공하는 인터페이스로, 이를 상속해 엔티티를 관리(생성, 조회, 수정, 삭제)할 수 있습니다. 
<br>
해당 인터페이스는 2개의 제네릭 요소를 받습니다. 하나는 관리할 대상 엔티티의 클래스 타입이고, 또 다른 하나는 그 엔티티의 대푯값 타입입니다.
<br>
<br>
( ㉢ )은/는 스프링 부트에서 제공하는 어노테이션으로, 이를 컨트롤러의 필드에 부여할 수 있습니다.
<br>
해당 어노테이션은 스프링 부트가 만들어 놓은 객체를 가져와 주입해 줍니다.


<br>
<br>
<br>
✔️
<br>

**답**
3번
<br>
해설: 확장자는 빼고 작성해야한다.
<br>
<br>

## 문제3 && 문제 풀이3
___
**3. 다음 ㉠~㉤에 들어갈 알맞은 용어를 쓰세요.**

<br>
<br>

(  ㉠  ): DB에서 데이터를 저장하는 틀
<br>
(  ㉡  ): 테이블의 행(row)을 표현하는 또 다른 말
<br>
(  ㉢  ): 데이터의 생성/조회/수정/삭제를 뜻하는 말
<br>
(  ㉣  ): 테이블에 데이터를 생성하는 SQL 문
<br>
(  ㉤  ): 테이블에 데이터를 조회하는 SQL 문
<br>
<br>

① INSERT
<br>
② 테이블
<br>
③ SELECT
<br>
④ CRUD
<br>
⑤ 레코드
<br>
<br>
<br>

✔️
<br>
**답**
<br>
㉠ layout
<br>
㉡ 부트스트랩
<br>
㉢ 템플릿화
<br>
<br>

## 문제4 && 문제 풀이4
___
**4. <회원 가입 페이지> 코드가 다음과 같을 때 컨트롤러, DTO, 엔티티, 리파지터리 구현하기.**

<br>
<br>

1. 컨트롤러: controller/MemberController.java

2. DTO: dto/MemberForm.java

3. 엔티티: entity/Member.java

4. 리파지터리: repository/MemberRepository.java


<br>
<br>
<br>

![첨부2](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0509_2.png?raw=true)
<br>
![첨부3](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0509_3.png?raw=true)
<br>
✔️
<br>
<br>
<br>
![첨부4](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0509_1.png?raw=true)