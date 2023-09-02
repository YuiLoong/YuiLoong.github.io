## 자바 컬렉션 프레임워크(4)
  이전 포스팅들과 같이 `컬렉션 프레임워크` 문제를 계속해서 풀어나갈 예정이다.(이후 포스팅도 마찬가지) <br>
  
  
## 문제
___
+ ArrayList 컬렉션 활용

Scanner를 사용하여 학점('A', 'B', 'C', 'D', 'F')을 5개만 문자로 입력받아 ArrayList에 저장하라.<br> 
그리고나서 다시 ArrayList를 검색하여 5개의 학점을 점수(A=4.0, B=3.0, C=2.0, D=1.0, F=0.0)로<br> 
변환하여 출력하는 프로그램을 작성하라.<br>
<br>
<br>

```
실행 결과
___
빈칸으로 분리하여 5개의 학점을 입력(A/B/C/D/F)>> B A F C D
3.0 4.0 0.0 2.0 1.0
```

## 문제 풀이 들어가기 전
  ___
  느낌이 오는가? ~~사실 느낌이 안 와도 문제에서 떡하니 `ArrayList 컬렉션` 이라고 친절하게 알려주었다.~~
  <br>
  그럼 바로 빠르게 문제 풀이에 들어가보도록 하자.
  
## 문제 풀이
  ___
  ~~이렇게 변수명/클래스명 등을 지정해주지 않는 경우, 많은 개발자들이 고민하게 되는 순간이다.~~
  <br>
  값을 출력하면 되는 문제로 클래스명은 간단하게 Print로 하겠다.<br>
  5개의 입력을 받으므로 for문을 돌려 5번 반복을 한다.<br>
  디테일하게 접근하자면, 출력 값 이전에 실행을 시키면<br> 
  `빈칸으로 분리하여 5개의 학점을 입력(A/B/C/D/F)`(이)가 나와야 한다
  <br>
  <br>
  그러므로 for문(입력 값 받기) 전에 저 문구를 출력 시키도록 배치를 하면 되겠다.<br>
  for문으로 입력을 받을 때 주의 사항이 있다.<br>
  단순히 값을 입력 받는 것에 그치는 것이 아닌<br>
  <span style="color:#2D3748;background-color:#fff5b1;">List에 객체를 추가할 필요가 있다.</span>
  <br> 그렇지않으면 오류가 나버린다..!
  <br>
  <br>
  좀 다른 방식으로 접근을 하였다.<br>
  다시말해, 이미 객체를 추가한 상태에서 for문을 돌려 입력 값과 판별하여 뽑아내는 것이 아닌<br>
  <span style="color:#2D3748;background-color:#fff5b1;">입력 값을 List에 추가하고 추가된 객체를 for문을 돌려 판별한 것이다.</span>
  <br>
  판별할 때는 한 문자 `equals`메소드를 사용한다. 
  
```js
// file: `Print.js`
import java.util.*;
public class Print {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		ArrayList<Character> score = new ArrayList<Character>();
		
		System.out.print("빈칸으로 분리하여 5개의 학점을 입력(A/B/C/D/F)>>");
		for(int i = 0; i < 5; i++) {
			char grade = sc.next().charAt(0);
			score.add(Character.valueOf(grade));	//a.add(grade);
		}
		
		
		for(int i = 0; i < 5; i++) {
			if(score.get(i).equals('A')) System.out.print(4.0+" ");
			else if(score.get(i).equals('B')) System.out.print(3.0+" ");
			else if(score.get(i).equals('C')) System.out.print(2.0+" ");
			else if(score.get(i).equals('D')) System.out.print(1.0+" ");
			else if(score.get(i).equals('F')) System.out.print(0.0+" ");
		}
		
		sc.close();
	}
}
```
  <br>
  이를 실행을 해보면 문제가 요구한 실행 결과처럼 뜰 것이다. :)
