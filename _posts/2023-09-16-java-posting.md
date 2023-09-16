---
categories: Java
---

## 자바 스트림 요소 처리(1)
  이번 포스팅부턴 `스트림 요소 처리`를 이용한 문제를 풀어나갈 예정이다.(이후 포스팅도 마찬가지) <br>
  ~~드디어 새로운 챕터이다..~~
  
  
## 문제
___
다음 문자열 배열에 대해 각 문자열 길이를 구해 출력하시오<br>
> String[] strArr = {"aaa", "bb", "c", "dddd"};
> 

```
실행 결과
___
3
2
1
4
```

## 문제 풀이 들어가기 전
  ___
  이번 문제는 푸는 방법이 다양하게 나올 수 있으나 `스트림 요소 처리`로 접근하여<br>
  요소 변환(매핑)을 하여 푸는 방식으로 가보도록 하겠다.<br>
  <br>
  <br>
 
  그렇다면 바로 문제 풀이에 들어가보자.<br>
  <br>
  
## 문제 풀이
  ___
  문자열 배열을 스트림으로 먼저 변환을 해준다.<br>
  이때 입력값이 배열이므로 `Arrays.stream`로 변경해준다.<br>
  
```js
// file: `Main.js`
import java.util.Arrays;

public class Main {
    public static void main(String[] args) {
    	
        String[] strArr = {"aaa", "bb", "c", "dddd"};

        Arrays.stream(strArr)                // 문자열 배열을 스트림으로 변환
              .map(str -> str.length())      // 각 문자열의 길이를 구함
              .forEach(str -> System.out.println(str)); // 결과 출력
    }
}
```
  <br>
  이를 실행을 해보면 문제가 요구한 실행 결과처럼 뜰 것이다. :)
