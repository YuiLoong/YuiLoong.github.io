## 자바 컬렉션 프레임워크(2)
  이전 포스팅과 같이 `컬렉션 프레임워크` 문제를 계속해서 풀어나갈 예정이다.(이후 포스팅도 마찬가지) <br>
  
  
## 문제
___
+ HashSet에 Student 객체를 저장하려고 함<br>
  학번이 같으면 동일한 Student라고 가정하고 중복 저장이 되지 않도록 한다<br>
  Student 클래스에서 재정의해야 하는 hashCode()와 equals() 메소드의 내용을 채워보기<br>
  (Student의 해시코드는 학번이라고 가정한다.)
  
```js
// file: `HashSetExample.js`
import java.util.Set;
import java.util.HashSet;

public class HashSetExample {
 
    public static void main(String[] args) {
        Set<Student> set = new HashSet<Student>();
 
        set.add(new Student(1, "홍길동"));
        set.add(new Student(2, "신용권"));
        set.add(new Student(1, "조민우")); //학번이 같으므로 저장되지 않음
 
        System.out.println("저장된 객체 수: " + set.size());

        for(Student s : set) {
        	System.out.println(s.studentNum + ":" + s.name);
        }
    }
}
```
```js
// file: `Student.js`

class Student {
    public int studentNum;
    public String name;
    public Student (int studentNum, String name) {
        this.studentNum = studentNum;
        this.name = name;
    }
    //여기에 코드를 작성!!
}
```
```
실행 결과
___
저장된 객체 수: 2
1:홍길동
2:신용권
```

## 문제 풀이 들어가기 전
  ___
  문제에서 떡하니 `HashSet`이라고 친절히 설명해줬다.<br>
  그렇다면 풀이에 들어가기 앞서 `HashSet`에 대해 알아보도록 하자
  <br>
  <br>
  <span style="color:#2D3748;background-color:#fff5b1;">HashSet</span> 은 지난 포스팅에 나왔던 [ArrayList] 와는 다른 `Set 컬렉션`이다. <br>
  `Set 컬렉션`은 저장 순서는 유지 되지만, 중복이 안된다는 특징이 있다.<br>
  이러한 성격을 가진 Set 컬렉션에서 자주 사용하는 것이 바로 `HashSet 컬렉션` 이다.<br>
  <br>
  그렇다면 HashSet 컬렉션의 생성 방법을 알아보도록 하자.<br>

## HashSet 컬렉션 생성 방법
  > Set<예시> set = new Set<예시> (); <br>
  > Set<예시> set = new Set<>();

  `ArrayList` 처럼 뒤에 `예시` 부분을 생략할 수 있다.<br>
  그리고 이번에도 주의할 점은 똑같다.<br>
   > Set set = new Set();
  <br>
 경우는 <span style="color:red">모든 타입의 객체를 저장</span> 한다는 점!


  [ArrayList]:https://yuiloong.github.io/2023-09-02-java-posting/#%EB%AC%B8%EC%A0%9C-%ED%92%80%EC%9D%B4
  
## 문제 풀이
  ___
  이번에는 코드 삽입만 하면 끝나기 때문에 간단한 문제라고 볼 수 있다.<br>
  문제에서 <U>학번이 같으면 중복 저장 X</U>라고 했기 떄문에 판별 해주는 코드를 넣으면 되는 문제<br>
  
```js
// file: `Student.js`
class Student {
    public int studentNum;
    public String name;
    
    public Student (int studentNum, String name) {
        this.studentNum = studentNum;
        this.name = name;
    }
    
    @Override
    public boolean equals(Object obj) {
        if (obj instanceof Student s) {
            if (s.studentNum == studentNum) {
                return true;
            } else {
                return false;
            }
        } else {
            return false;
        }
    }
    @Override
    public int hashCode() {
        return studentNum;
    }
}
```
  추가적으로 설명할 게 있다. `Java12` 버전부터는 우측 타입 변수 사용이 가능하기에 강제 형변환 필요가 없다<br>
  물론, 
   

  ```js
// file: `Student.js`
 if (obj instanceof Student) {
            Student student = (Student) obj;
            if (student.studentNum == studentNum) {
            }
  }
```
  처럼 형변환을 해서 사용해도 된다.
  
  <br>
  이를 실행을 해보면 문제가 요구한 실행 결과처럼 뜰 것이다. :)
