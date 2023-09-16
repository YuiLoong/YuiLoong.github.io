---
categories: Java
---

## 자바 스트림 요소 처리(3)
  이번 포스팅도 `스트림 요소 처리`를 이용 문제를 풀어나갈 예정이다.(이후 포스팅도 마찬가지) <br>

  
  
## 문제
___
List에 저장되어 있는 Member들을 이름순으로 정렬해 출력하시오<br>
(힌트: 문자열 비교로는 String 클래스의 compareTo() 메소드를 사용)<br>
  
```js
// file: `MemberExample.js`

import java.util.Arrays;
import java.util.List;

public class MemberExample {
	 public static void main(String[] args) {

	        List<Member> list = Arrays.asList(
	            new Member("홍길동", 30),
	            new Member("이순신", 40),
	            new Member("강감찬", 26)
	        );
	        list.stream()
	        //여기에 코드 삽입!
	     }
}
class Member {

    private String name;
    private int age;

    public Member(String name, int age) {
        this.name = name;
        this.age = age;
    }
    public String getName() { return name; }
    public int getAge() { return age; }

}

```
```
실행 결과
___
강감찬: 26
이순신: 40
홍길동: 30
```
  
## 문제 풀이
  ___
  이번 문제는 "이름순"으로 즉, 문자열 비교 문제이다.<br>
  문자열 간의 비교는 `compareTo()`함수를 이용하면 된다!<br>
  <br>
  compareTo() 함수를 이용하여 앞-뒤 문자열 비교를 해준 뒤,<br>
  sort()를 통해 정렬을 해준다.<br>
  
```js
// file: `MemberExample.js`
import java.util.Arrays;
import java.util.List; 
public class MemberExample {
	 public static void main(String[] args) {

	        List<Member> list = Arrays.asList(
	            new Member("홍길동", 30),
	            new Member("이순신", 40),
	            new Member("강감찬", 26)
	        );
	        list.stream()
	        .sorted((m1, m2) -> m1.getName().compareTo(m2.getName())) // 이름으로 정렬
          .forEach(member -> System.out.println(member.getName() + ": " + member.getAge()));
	     }
}
class Member {

    private String name;
    private int age;

    public Member(String name, int age) {
        this.name = name;
        this.age = age;
    }
    public String getName() { return name; }
    public int getAge() { return age; }

}
```
  <br>
  이를 실행을 해보면 문제가 요구한 실행 결과처럼 뜰 것이다. :)
