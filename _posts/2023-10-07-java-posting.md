---
categories: Java
---

## 데이터 입출력(1)
  이번 포스팅부턴 `데이터 입출력`을 이용한 문제를 풀어나갈 예정이다.(이후 포스팅도 마찬가지) <br>
  ~~벌써 10월이라니 시간이 참 빠른 것 같다..~~
  
## 문제
___
키보드로부터 합치고자 하는 파일의 개수를 입력받고, 그 개수만큼 파일명을 입력받아 1개 파일로 합쳐서 출력하는 프로그램을 작성하시오.<br>
만약 입력 파일이 존재하지 않으면 해당 파일이 존재하지 않는다는 메시지를 출력하시오.<br>
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
  ![첨부1](YuiLoong.github.io/assets/img/1007(1))
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
  <br>
  이를 실행을 해보면 문제가 요구한 실행 결과처럼 뜰 것이다. :)
  <br>
  추가로 파일을 열어보면 병합된 새 text파일이 추가된 것을 확인할 수 있다.
  <br>
  ![첨부1](YuiLoong.github.io/assets/img/1007(1))
