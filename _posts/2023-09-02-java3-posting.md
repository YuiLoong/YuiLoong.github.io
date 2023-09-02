## 자바 컬렉션 프레임워크(3)
  이전 포스팅들과 같이 `컬렉션 프레임워크` 문제를 계속해서 풀어나갈 예정이다.(이후 포스팅도 마찬가지) <br>
  
  
## 문제
___
+ HashMap에 아이디(String)와 점수(Integer)가 저장됨<br>
실행 결과와 같이 평균점수를 출력하고, 최고 점수와 최고 점수를 받은 아이디를 출력하기.
  
```js
// file: `MapExample.js`
import java.util.HashMap;
import java.util.Map;
import java.util.Set;
 
public class MapExample {
 
    public static void main(String[] args) {
        Map<String,Integer> map = new HashMap<String,Integer>();
        
        map.put("blue", 96);
        map.put("hong", 86);
        map.put("white", 92);
        
        String name = null; // 최고 점수를 받은 아이디 저장
        int maxScore = 0;    // 최고 점수 저장
        int totalScore = 0;    // 점수 합계 저장
        
        //여기에 코드 작성!!
    }
}
```

```
실행 결과
___
평균 점수: 91
최고 점수: 96
최고 점수를 받은 아이:blue
```

## 문제 풀이 들어가기 전
  ___
  그렇다 이번 문제는 `HashMap`을 이용한 문제이다.<br>
  그렇다면 풀이에 들어가기 앞서 `HashMap`에 대해 알아보는 시간을 짧게 가져보도록 하자.
  <br>
  <br>
  <span style="color:#2D3748;background-color:#fff5b1;">HashMap</span> 은 지난 포스팅에 나왔던 [HashSet] 과는 다른 `Map 컬렉션`이다. <br>
  그렇기에 다른 특징을 가지고 있다.<br>
  >키로 사용할 객체가 HashCode() 메소드의 리턴값이 같고<br>
  >equals() 메소드가 true를 리턴할 경우, 동일 키로 보고 중복 허용하지 않음
  
  이러한 성격을 가진 것이 `HashMap 컬렉션` 이다.<br>
  <br>
  그렇다면 HashMap 컬렉션의 생성 방법을 알아보도록 하자.<br>

## HashMap 컬렉션 생성 방법
  > Map<키 타입, 값 타입> map = new HashMap<키 타입, 값 타입> (); <br>

  생략 부분은 <span style="color:green">[HashSet]과는 다른 요구사항이 있다.</span>
  <br>
  <br>
  <u>Map에 지정된 키와 값의 타입이 HashMap과 동일할 경우이다.</u>
  <br>그리고 이번에도 주의할 점은 똑같다.<br>
   > Map map = Map map();
  <br>
  경우는 모든 타입의 객체를 저장한다는 점!
<br>
<span style="color:red">다만, 이런 경우는 거의 없다.</span>


  [HashSet]:https://yuiloong.github.io/2023-09-02-java2-posting/#%EB%AC%B8%EC%A0%9C-%ED%92%80%EC%9D%B4-%EB%93%A4%EC%96%B4%EA%B0%80%EA%B8%B0-%EC%A0%84
  
## 문제 풀이
  ___
  우선 Set 컬렉션을 얻는다<br>
  그리고 for문을 돌려 조건문을 통해 최고 점수 와 그 점수를 받은 아이디를 뽑아내고<br>
  조건문 밖으론 총 합계를 뽑아내어 평균을 낸다.<br>
  
```js
// file: `Student.js`
import java.util.HashMap;
import java.util.Map;
import java.util.Set;
 
public class MapExample {
 
    public static void main(String[] args) {
        Map<String,Integer> map = new HashMap<String,Integer>();
        
        map.put("blue", 96);
        map.put("hong", 86);
        map.put("white", 92);
        
        String name = null; // 최고 점수를 받은 아이디 저장
        int maxScore = 0;    // 최고 점수 저장
        int totalScore = 0;    // 점수 합계 저장
        
        Set<Map.Entry<String, Integer>> EntrySet = map.entrySet();
        for (Map.Entry<String, Integer> entry : EntrySet) {
            if (entry.getValue() > maxScore) {
                name = entry.getKey();
                maxScore = entry.getValue();
            }
            totalScore += entry.getValue();
        }
        int avgScore = totalScore / map.size();
        System.out.println("평균 점수 : "+ avgScore);
        System.out.println("최고 점수 : "+ maxScore);
        System.out.println("최고점수를 받은 아이디 : "+ name);
    }
}
```
  <br>
  이를 실행을 해보면 문제가 요구한 실행 결과처럼 뜰 것이다. :)
