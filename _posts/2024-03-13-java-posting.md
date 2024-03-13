---
categories: Java
toc: true
---

## 자바스크립트 변수와 자료형 연습문제(1)
  올해부턴 자바뿐만 아니라 `자바스크립트`를 공부하며 문제를 풀어나가 보려고 한다.<br>
  ~~한 것도 없는데 벌써 24년도 3월이랜다 올해는 진짜 정말 열심히 살아보도록 노력해야지 ..~~ <br>
  <br>
  이번 포스팅부턴 문제당 1포스팅이 아니라 <span style="color: #2D3748; background-color:#fff5b1;">한 포스팅에 여러문제</span>를 풀면서 공부하려고 합니다.
  <br>
  
## 문제1
___
알림창에 자신의 이름을 출력하는 코드를 작성해 보시오<br>
<br>
> **입력** <br>
> 실행예: 1 <br>
> 합칠 파일 개수 = <span style="color:green">3</span><br>
> 입력 파일명 1 = <span style="color:green">c:/temp/test1.txt</span><br>
> 입력 파일명 2 = <span style="color:green">c:/temp/test2.txt</span><br>
> 입력 파일명 3 = <span style="color:green">c:/temp/test3.txt</span><br>
> 출력 파일명 = <span style="color:green">c:/temp/result.txt</span><br>
> <span style="color:blue">완료되었습니다.</span><br>
> <br>
> 실행예: 2<br>
> 합칠 파일 개수 = <span style="color:green">3</span><br>
> 입력 파일명 1 = <span style="color:green">c:/temp/test1.txt</span><br>
> 입력 파일명 2 = <span style="color:green">c:/temp/test2.txt</span><br>
> 입력 파일명 3 = <span style="color:green">c:/temp/test4.txt</span><br>
> 출력 파일명 = <span style="color:green">c:/temp/result.txt</span><br>
> <span style="color:red">파일 c:/temp/test4.txt가 존재하지 않습니다.</span><br>
> <br>
>> **텍스트 파일 참조**<br>
>> test1.txt의 내용:<br>
>> 첫 번째 파일입니다.<br>
>> test2.txt의 내용:<br>
>> 세 번째 파일입니다.<br>
>>> **결과**<br>
>>> 정상적인 실행 시 result.txt의 내용:<br>
>>> 첫 번째 파일입니다.<br>
>>> 두 번째 파일입니다.<br>
>>> 세 번째 파일입니다.<br>


<br>
<br>

## 문제 풀이 들어가기 전
  ___
  이번 문제를 들어가기 앞서 미리 텍스트 파일을 만들어준다.<br>
  경로는 기억해두면 어디든 상관없으나, 일단 문제에서 예시로 든 경로를 기준으로 만들어보겠다. <br>
  <br>
  ![첨부1](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/1007(1).png?raw=true)
  <br>
  
## 문제 풀이
  ___
  이번 문제는 `BufferReader`를 이용해 풀어보려고한다.<br>
  `BufferReader`는 간단하게 말하자면 `Scanner`와 비슷하고 볼 수 있다.<br>
  다만,`Scanner`와 `BufferReader`의 경우는 입력 받은 데이터가 String 고정이기 때문에<br>
  따로 원하는 타입으로 입력 데이터를 가공해줘야한다.<br>
  그렇다면 왜 Scanner가 아닌 Buffer를 써야하나? 그 이유는 입력값이 많을 땐 성능적으로도<br>
  그렇고 무엇보다 Scanner보다 수행 시간이 빠르기 때문이다.<br>
  

```js
// file: `ReadExample.java`
import java.io.*;
import java.io.FileNotFoundException;

public class ReadExample {
    public static void main(String[] args) {
        try {
            BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
            
            System.out.print("합칠 파일 개수 = ");
            int cnt = Integer.parseInt(br.readLine());
            
            String[] inputFiles = new String[cnt]; //합칠 파일의 갯수만큼 공간 만들기
            
            for (int i = 0; i < cnt; i++) {
                System.out.print("입력 파일명 " + (i + 1) + " = ");
                inputFiles[i] = br.readLine();
            }
            
            System.out.print("출력 파일명 = ");
            String outputFileName = br.readLine();
            
            File outputFile = new File(outputFileName);
            
            try (FileWriter writer = new FileWriter(outputFile)) {
                for (String inputFileName : inputFiles) {
                    File inputFile = new File(inputFileName);
                    if (inputFile.exists()) {
                        try (BufferedReader reader = new BufferedReader(new FileReader(inputFile))) {
                            String line;
                            while ((line = reader.readLine()) != null) {
                                writer.write(line + "\n");
                            }
                        }
                    } else {
                        System.out.println("파일 " + inputFileName + "가 존재하지 않습니다.");
                    }
                }
            }
            
            System.out.println("완료되었습니다.");
            
        } catch (FileNotFoundException e) {
        	e.printStackTrace();
        }catch (IOException e) {
            e.printStackTrace();
        } 
    }
}
}

```
  이를 실행을 해보면 문제가 요구한 실행 결과처럼 뜰 것이다. :)
  <br>
  추가로 파일을 열어보면 병합된 새 text파일이 추가된 것을 확인할 수 있다.
  <br>
![첨부1](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/1007(2).png?raw=true)
