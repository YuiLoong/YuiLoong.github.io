---
categories: Java
---

## 자바 스트림 요소 처리(4)
  이번 포스팅도 `스트림 요소 처리`를 이용 문제를 풀어나갈 예정이다.(이후 포스팅도 마찬가지) <br>

  
  
## 문제
___
스트림을 이용해서 문자열 배열 strArr의 모든 문자열의 길이를 더한 결과를 출력하시오.<br>
  
```js
// file: `StringSumLength.js`


import java.util.Arrays;

import java.util.stream.Stream;

 

public class StringSumLength {

    public static void main(String[] args) {

        String[] strArr = {"aaa", "bb", "c", "dddd"};
          //여기에 코드 추가
        System.out.println("sum=" + sum);

    }

}

```
```
실행 결과
___
sum=10
```
  
## 문제 풀이
  ___
  이번 문제는 문자열들의 각 길을 합산하여 결과를 출력하는 문제다.<br>
  그러므로 문자열 배열을 스트림으로 변환해준 뒤<br>
  각 길이를 매핑하고 합산을 해주면 된다.<br>
  <br>
  
```js
// file: `MemberExample.js`
import java.util.Arrays;
import java.util.stream.Stream;

public class StringSumLength {

    public static void main(String[] args) {
        String[] strArr = {"aaa", "bb", "c", "dddd"};

        // 스트림으로 변환
        Stream<String> stringStream = Arrays.stream(strArr);

        // 매핑 및 합산
        int sum = stringStream.mapToInt(String::length).sum();

        System.out.println("sum=" + sum);
    }
}

```
  <br>
  이를 실행을 해보면 문제가 요구한 실행 결과처럼 뜰 것이다. :)
