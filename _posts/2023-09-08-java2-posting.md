---
categories: Java
---

## 자바 컬렉션 프레임워크(8)
  이전 포스팅들과 같이 `컬렉션 프레임워크` 문제를 계속해서 풀어나갈 예정이다.(이후 포스팅도 마찬가지) <br>
  
  
## 문제
___
다음의 StudentComparator 클래스를 완성하여<br>
TreeSet에 담긴 Student 인스턴스들이 총점(total)에 따라 오름차순 정렬되게 하시오.<br>

```js
// file: `StudentExample.js`
import java.util.TreeSet;

class Student {

    String name;
    int no;
    int kor, eng, math, total;
 

    public Student(String name, int no, int kor, int eng, int math) {

        this.name = name;
        this.no = no;
        this.kor = kor;
        this.eng = eng;
        this.math = math;
        this.total = getTotal();

    }

    int getTotal() {
        return kor+eng+math;
    }

    double getAverage() {
        return Math.round(getTotal()/3.0*10)/10.0;
    }

    public String toString() {
        return name + "," + no + "," + kor + "," + eng + "," + math + "," + getTotal() + "," + getAverage();
    }
}

class StudentComparator{
      //여기 코드 작성
}

public class StudentExample {

    public static void main(String[] args) {

        TreeSet<Student> treeSet = new TreeSet<>(new StudentComparator());

        treeSet.add(new Student("홍길동",1,100,100,100));
        treeSet.add(new Student("이순신",2,90,70,80));
        treeSet.add(new Student("김자바",3,80,80,90));
        treeSet.add(new Student("이자바",4,70,90,70));
        treeSet.add(new Student("박자바",5,60,100,60));

        for (Student student : treeSet) {
            System.out.println(student);
        }        
    }
}
```
```
실행 결과
___
박자바,5,60,100,60,220,73.3
이자바,4,70,90,70,230,76.7
이순신,2,90,70,80,240,80.0
김자바,3,80,80,90,250,83.3
홍길동,1,100,100,100,300,100.0
```

## 문제 풀이 들어가기 전
  ___
  이번 문제는 이전 포스팅과 같은 문제이다.<br>
  [이전 문제]는 이름이 기준이었다면 이번에는 <span style="color:red">총점</span>이 기준인 문제이다.<br>
  <br>
  <br>
 
  그렇다면 바로 문제 풀이에 들어가보자.<br>
  <br>

  [이전 문제]:https://yuiloong.github.io/java/2023-09-08-java-posting/
  
## 문제 풀이
  ___
  총점에 따라 오름차순 정렬을 위해 `TreeSet`에 `Comparator`를 사용한다.<br>
  마찬가지로 StudentComparator클래스가 Comparable 인터페이스를 구현하도록 변경해준다.<br>
  그리고 `Compare` 메소드를 이용하여 두 총점을 비교한다.<br>
  
```js
// file: `StudentExample.js`
import java.util.TreeSet;
import java.util.Comparator;

class Student {

    String name;
    int no;
    int kor, eng, math, total;
 

    public Student(String name, int no, int kor, int eng, int math) {

        this.name = name;
        this.no = no;
        this.kor = kor;
        this.eng = eng;
        this.math = math;
        this.total = getTotal();

    }

    int getTotal() {
        return kor+eng+math;
    }

    double getAverage() {
        return Math.round(getTotal()/3.0*10)/10.0;
    }

    public String toString() {
        return name + "," + no + "," + kor + "," + eng + "," + math + "," + getTotal() + "," + getAverage();
    }
}

class StudentComparator implements Comparator<Student> {

	 @Override
	 public int compare(Student s1, Student s2) {
		 return Integer.compare(s1.getTotal(),s2.getTotal());
	 }
}

public class StudentExample {

    public static void main(String[] args) {

        TreeSet<Student> treeSet = new TreeSet<>(new StudentComparator());

        treeSet.add(new Student("홍길동",1,100,100,100));
        treeSet.add(new Student("이순신",2,90,70,80));
        treeSet.add(new Student("김자바",3,80,80,90));
        treeSet.add(new Student("이자바",4,70,90,70));
        treeSet.add(new Student("박자바",5,60,100,60));

        for (Student student : treeSet) {
            System.out.println(student);
        }        
    }
}
```
  <br>
  이를 실행을 해보면 문제가 요구한 실행 결과처럼 뜰 것이다. :)
