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


## 문제 풀이1
  ___
  <br>
  먼저 `Visual Code`에서 임의의 html파일을 생성하고 웹 브라우저를 불러온 뒤 그림과 같이 콘솔창을 띄운다.
  ![첨부1](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0313_1.png?raw=true)
  <br>
  그 다음 콘솔창에 `alert() 함수`를 이용해 자신의 이름을 출력해보자.<br>
  <br>

> **alert()함수** <br>
> alert문은 알림창을 표시한다. 그리고 이 함수의 소괄호 안에 메시지나 변수를 넣으면 알림창에 텍스트나 변숫값이 뜬다.<br>
> <span style="color:green">이때 소괄호 안에 큰 따옴표나 작은 따옴표와 함께 작성해줘야한다.</span><br>

  <br>
  <br>
  이름을 출력해야하므로 소괄호 안에 자신의 이름을 넣어준다.<br>
  <br>
  ![첨부2](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0313_2.png?raw=true)
  <br>
  <br>
  그리고 `Enter`키를 눌러주면 화면처럼 알림창에 텍스트가 뜬다.<br>
  ![첨부3](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0313_3.png?raw=true)
  <br>
  <br>
  

## 문제2
___
다음의 코드를 실행하여 나오는 '확인 창'에서 [확인] 버튼을 클릭했을 때 반환되는 값은 무엇인가?<br>
```js
//

confirm('프로그램을 종료하시겠습니까?');

```
<br>
<br>
  
## 문제 풀이2
  ___
  ![첨부4](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0313_4.png?raw=true)
  <br>
  <br>
  사진처럼 `true`가 나온다.<br>
  추가로 `취소`를 누를 경우, `false`가 나온다.<br>
  <br>
  
## 문제3
___
콘솔 창에 '자바스크립트를 좋아합니다'라고 출력하는 코드를 작성해 보시오.<br>
<br>
<br>

## 문제 풀이3
  ___
  <br>
  콘솔창에 출력하는 문제는 `console.log() 명령을 사용해서 하면 된다.
  <br>
  <br>

> **console.log()함수** <br>
> 간단하게 텍스트로 보여주는 명령<br>
> 중간중간 프로그램이 제대로 동작하는 지 확인하는 용도<br>
> <span style="color:green">이때 소괄호 안에 큰 따옴표와 함께 작성해줘야한다.</span><br>
  <br>
  <br>

문제에서 요구한 대로 콘솔 창에 메시지를 출력해야하므로 소괄호 안에 텍스트를 넣어준다.<br>
코드를 작성한 뒤, `Enter` 키를 눌러주면 사진과 같이 결과값이 창이 아닌 콘솔창에 뜬다.<br>
<br>
![첨부5](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0313_5.png?raw=true)
<br>
<br>

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
