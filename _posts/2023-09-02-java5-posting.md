---
categories: Java
---

## 자바 컬렉션 프레임워크(5)
  이전 포스팅들과 같이 `컬렉션 프레임워크` 문제를 계속해서 풀어나갈 예정이다.(이후 포스팅도 마찬가지) <br>
  
  
## 문제
___
+ Vector 컬렉션 활용
Scanner를 사용하여 5개의 실수값을 사용자로부터 입력받아 벡터에 저장<br>
그리고나서 벡터를 검색하여 가장 큰 수를 출력하는 프로그램을 작성하라.<br>
(힌트: 빈칸으로 분리된 실수를 하나씩 읽으려면 scanner.nextDouble()을 사용하세요.)

```
실행 결과
___
숫자 5개 입력>> 3.14 2.2 5.5 99.9 33.7
가장 큰 수는 99.9
```

## 문제 풀이 들어가기 전
  ___
  이번 문제는 조금 새롭다. 바로 `Vector`(을)를 이용한 문제이다.<br>
  그러나 그렇게 어려워할 필요가 없다.<br>
  `Vector`는 [ArrayList]와 동일한 내부 구조를 가지고 있기 때문이다.<br>
  <br>
  <br>
  <span style="color:#2D3748;background-color:#fff5b1;">다만, 멀티 스레드가 동시에 Vector() 메소드를 실행할 수 없다.</span> 
  <br>
  라는 차이점이 있으니 참고하자.<br>
 
  그렇다면 바로 문제 풀이에 들어가보자자.<br>


  [ArrayList]:https://yuiloong.github.io/2023-09-02-java-posting/#%EB%AC%B8%EC%A0%9C-%ED%92%80%EC%9D%B4
  
## 문제 풀이
  ___
  문제 자체가 난이도가 그리 높지 않으니 별다른 얘기는 없지만, 주의할 점이 있다.<br>
  바로  <span style="color:red">실수 값</span>이라는 것이다. <br>
  그러므로 `Integer`가 아닌 `Double`로 받아야한다.<br>
  
```js
// file: `Max.js`
import java.util.*;

public class Max {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		Vector<Double> v = new Vector<Double>();
		
		System.out.print("숫자 5개 입력>> ");
		for(int i=0;i<5;i++) {
			double n = sc.nextDouble();
			v.add(n);
		}
		
		double max = v.get(0);
		for(int i = 0; i < v.size(); i++) {
			if (max < v.get(i)) max = v.get(i);
		}
		
		System.out.println("가장 큰 수는 " + max);
		
		sc.close();
	}
}
```
  <br>
  이를 실행을 해보면 문제가 요구한 실행 결과처럼 뜰 것이다. :)
