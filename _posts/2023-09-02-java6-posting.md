## 자바 컬렉션 프레임워크(6)
  이전 포스팅과 같이 `컬렉션 프레임워크` 문제를 계속해서 풀어나갈 예정이다.(이후 포스팅도 마찬가지) <br>
  하루에 꽤 되는 포스팅을 올렸다... 오늘은 이 포스팅으로 마무리하고자 한다.
  
  
## 문제
___
+ HashMap 컬렉션 활용

HashMap<String, Integer> 컬렉션을 생성하고<br> 
"에스프레소"는 2000, "아메리카노"는 2500, "카푸치노"는 3000, "카페라떼"는 3500을 저장하라.<br>
그리고 다음과 같이 음료수 이름을 입력받으면 HashMap에서 검색하여 가격을 출력하라.<br>
  
```
실행 결과
___
에스프레소, 아메리카노, 카푸치노, 카페라뗴가 있습니다.
주문 >> 아메리카노
아메리카노는 2500입니다.
주문 >> 카푸치노
카푸치노는 3000입니다.
주문 >> 그만
```

## 문제 풀이 들어가기 전
  ___
  이 문제는 친절하게도 [HashMap]을 이용한 문제이므로 바로 문제 풀이에 들어가겠다.
<br>
<br>

  [HashMap]:https://yuiloong.github.io/2023-09-02-java3-posting/#hashmap-%EC%BB%AC%EB%A0%89%EC%85%98-%EC%83%9D%EC%84%B1-%EB%B0%A9%EB%B2%95
  
## 문제 풀이
  ___
  
  문제 설명에선 얘기가 없었지만, 실행 결과를 보면 알 수 있다.<br>
  특정 키워드인 "그만"을 입력하면 프로그램이 종료된다.<br>
  그렇다는 것은 그 전까진 계속 반복해야한다는 것으로 <span style="color:red">무한 루프를</span> 쓰는 것이 좋겠다.<br>
  <br>
  추가로 문제에선 요구하지 않았으나 디테일적으로 입력되지 않은<br>
  메뉴를 입력했을 경우를 생각하여 예외 처리를 해두었다.
   

  ```js
// file: `Menu.js`
import java.util.HashMap;
import java.util.Scanner;

public class Menu {
    public static void main(String[] args) {
        HashMap<String, Integer> menu = new HashMap<String, Integer>();
        menu.put("에스프레소", 2000);
        menu.put("아메리카노", 2500);
        menu.put("카푸치노", 3000);
        menu.put("카페라떼", 3500);

        System.out.println("에스프레소, 아메리카노, 카푸치노, 카페라떼가 있습니다.");
        
        Scanner scanner = new Scanner(System.in);

        while (true) {
            System.out.print("주문 >> ");
            String order = scanner.nextLine();

            if (menu.containsKey(order)) {
                int price = menu.get(order);
                System.out.println(order + "는 " + price + "입니다.");
            } else if (order.equals("그만")) {
                break;
            } else {
                System.out.println("그런 메뉴는 없습니다.");
            }
        }

        scanner.close();
    }
}

```
  
  <br>
  이를 실행을 해보면 문제가 요구한 실행 결과처럼 뜰 것이다. :)

    permalink:         /:Java/
    
    permalink:         /tag-:프레임워크/
