---
categories: Java
toc: true
toc_sticky: true
---

## 데이터 입출력(3)
  이번 포스팅도 `데이터 입출력`을 이용한 문제다.(이후 포스팅도 마찬가지) <br>
  
## 문제
___
File 클래스를 활용하여 C:\에 있는 파일(디렉터리 제외) 중에서 크기가 제일 큰 파일의 이름을 출력하시오.<br>


```
실행 결과
___
가장 큰 파일은 pagefile.sys 375064576바이트
```


<br>
<br>

## 문제 풀이
  ___
  이번 문제는 for문을 돌려주며 크기를 비교하면 되는 문제이므로 .<br>
  따로 설명없이 바로 문제를 풀어보도록 하겠다.<br>
  <br> 
  

```js
// file: `FileName.java`

import java.io.File;

public class FileName {
	public static void main(String[] args) {
		File file = new File("C:\\");
		File[] subFiles = file.listFiles();
		long max = 0;
		String name = "";
		for(int i=0;i<subFiles.length;i++) {
			File temp = subFiles[i];
			if(max < temp.length()) {
				max = temp.length();
				name = temp.getName();
			}
		}
		System.out.println("가장 큰 파일은"+name+" "+max+"바이트");
	}
}

```
  이를 실행을 해보면 문제가 요구한 실행 결과처럼 뜰 것이다. :)
  <br>
  
