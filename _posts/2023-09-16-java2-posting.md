---
categories: Java
---

## 자바 스트림 요소 처리(2)
  이번 포스팅부턴 `스트림 요소 처리`를 이용한 문제를 풀어나갈 예정이다.(이후 포스팅도 마찬가지) <br>
  ~~드디어 새로운 챕터이다..~~
  
  
## 문제
___
다음과 같이 정수가 저장된 배열에서 스트림을 이용해 중복을 제거하고 오름차순으로 정렬해 출력하시오.<br>
> int[] arr = {20, 25, 1, 33, 25, 35, 42, 33};
> 

<br>
<br>

## 문제 풀이 들어가기 전
  ___
  이번 문제도 딱히 어려움이 없는 문제이기 때문에 바로 들어가보도록 하겠다.<br>
  <br>
  <br>
  <br>
  
## 문제 풀이
  ___
  이 문제도 지난 포스팅과 같이 배열을 받는다.<br>
  중복 제거는 distinct() 메서드를 사용하므로 기억해두면 좋다.<br>
  distinct는 DB에서도 쓰여서 낯설기보단 반가웠다.
  
```js
// file: `Main.js`
import java.util.Arrays;

public class Main {
    public static void main(String[] args) {
        int[] arr = {20, 25, 1, 33, 25, 35, 42, 33};

        Arrays.stream(arr)        // 정수 배열을 스트림으로 변환
              .distinct()         // 중복 제거
              .sorted()           // 오름차순 정렬
              .forEach(System.out::println); // 결과 출력
    }
}

```
  <br>
  이를 실행을 해보면 문제가 요구한 실행 결과처럼 뜰 것이다. :)
