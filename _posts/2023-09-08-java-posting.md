---
categories: Java
---


## 자바 컬렉션 프레임워크(7)
  오늘도 이전 포스팅과 같이 `컬렉션 프레임워크` 문제를 계속해서 풀어나갈 예정이다.(이후 포스팅도 마찬가지) <br>
  
  
## 문제
___
Student 클래스가 Comparable 인터페이스를 구현하도록<br>
변경해서 이름(name)이 기본 정렬 기준이 되게 하시오.<br> 


  ```js
// file: `StudentExample.js`
import java.util.TreeSet;

class Student {

    String name;
    int no;
    int kor, eng, math;

    public Student(String name, int no, int kor, int eng, int math) {
        this.name = name;
        this.no = no;
        this.kor = kor;
        this.eng = eng;
        this.math = math;
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

public class StudentExample {

    public static void main(String[] args) {

        TreeSet<Student> treeSet = new TreeSet<>();

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
김자바,3,80,80,90,250,83.3
박자바,5,60,100,60,220,73.3
이순신,2,90,70,80,240,80.0
이자바,4,70,90,70,230,76.7
홍길동,1,100,100,100,300,100.0
```

## 문제 풀이 들어가기 전
  ___
  문제에서 'Comparable 인터페이스를 구현하도록' 하였다.<br>
  그럼 간단하게 Comparable에 관련해서 알아보도록 하자.<br>
<br>
<br>

## Comparable / Comparator
  ___
  TreeSet과 TreeMap에 저장되는 키, 객체는 저장과 동시에 오름차순으로 정렬되는데,<br>
  Comparable 인터페이스를 구현하고 있어야 가능함<br>
  또한 compareTo() 메소드가 정의 되어 있다.<br>
  따라서 사용자 정의 클래스에서 이 메소드를 재정의하여 비교 결과를 정수 값으로 리턴해야 함
  <br>
  <br>
  
## 문제 풀이
  ___
  
  <br>
  문제에서 요구한 대로 하면 되는 문제.<br>
  <span style="color:red">이름이 기본 정렬 기준</span>인 것을 확인해두기.<br>
  <br>
   

  ```js
// file: `StudentExample.js`
import java.util.TreeSet;

class Student implements Comparable<Student> {

    String name;
    int no;
    int kor, eng, math;

    public Student(String name, int no, int kor, int eng, int math) {
        this.name = name;
        this.no = no;
        this.kor = kor;
        this.eng = eng;
        this.math = math;
    }    

    int getTotal() {
        return kor + eng + math;
    }

    double getAverage() {
        return Math.round(getTotal() / 3.0 * 10) / 10.0;
    }
    
    public String toString() {
        return name + "," + no + "," + kor + "," + eng + "," + math + "," + getTotal() + "," + getAverage();
    }

    @Override
    public int compareTo(Student s) {
        return this.name.compareTo(s.name);
    }
}

public class StudentExample {

    public static void main(String[] args) {

        TreeSet<Student> treeSet = new TreeSet<>();

        treeSet.add(new Student("홍길동", 1, 100, 100, 100));
        treeSet.add(new Student("이순신", 2, 90, 70, 80));
        treeSet.add(new Student("김자바", 3, 80, 80, 90));
        treeSet.add(new Student("이자바", 4, 70, 90, 70));
        treeSet.add(new Student("박자바", 5, 60, 100, 60));

        for (Student student : treeSet) {
            System.out.println(student);
        }
    }
}


```
  
  <br>
  이를 실행을 해보면 문제가 요구한 실행 결과처럼 뜰 것이다. :)
