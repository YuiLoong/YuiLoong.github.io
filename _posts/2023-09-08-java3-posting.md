---
categories: Java
---

## 자바 컬렉션 프레임워크(9)
  오늘은 이 문제를 마지막으로 `컬렉션 프레임워크` 끝낼 계획이다.<br>
  
  
## 문제
___
로또 번호 생성기를 제작한다.<br>
여러 가지 방법이 있으나 다음 방법으로 만들어 보자.<br>

> 1) 1부터 45까지 저장하는 리스트를 생성한다.<br>
>
> 2) 리스트를 섞는다.<br>
>
> 3) 앞 6개 번호를 출력한다.<br>

  <br>

## 문제 풀이 들어가기 전
  ___
  이번 문제는 Collection 클래스 문제이다.<br>
  문제 풀이에 들어가기 앞서 간단하게 알아보도록 하자.<br>
  <br>

 ## Collection 클래스
 ___
 컬렉션 객체에 대해 정렬/섞기/검색 등의 여러 기능들을 수행하는 정적 메소드를 제공한다.<br>
 정적 메소드를 제공하므로 객체 생성 없이 사용 가능하다.<br>

<br>
<br>

## 문제 풀이
  ___
  간단한 문제이다. 우선 1~45까지를 저장하는 리스트를 생성하기 위해<br>
  1~45까지 도는 for문을 만들어주어 리스트에 집어넣는다.<br>
  그리고 `Suffle` 메소드를 사용하여 섞어준다.<br>
  마지막으로 6개의 랜덤 숫자를 추출하기 위해 0~5까지의 for문을 만들어준다.
  
```js
// file: `Suffle.js`
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

public class Suffle {
	public static void main(String[] args) {
		List<Integer> list = new ArrayList<Integer>();
		for(int i=1;i<=45;i++) {
			list.add(i);
		}
		Collections.shuffle(list);
		for(int i=0;i<6;i++) {
			System.out.print(list.get(i)+" ");
		}
	}
}
```
  <br>
  이를 실행을 해보면 문제가 요구한 실행 결과처럼 뜰 것이다. :)
