---
categories: Java
toc: true
---

## 데이터 입출력(2)
  이번 포스팅도 `데이터 입출력`을 이용한 문제다.(이후 포스팅도 마찬가지) <br>
  
## 문제
___
다음은 디렉터리의 요약정보를 보여주는 프로그램이다.<br>
파일의 개수, 디렉터리의 개수, 파일의 총 크기를 계산하는 countFiles()를 완성하시오.<br>

 ```js
// file: `DirectoryInfo.java`
import java.io.File;
import java.util.Scanner;

	public class DirectoryInfo {
	
	    static int totalFiles = 0;
	    static int totalDirs = 0;
	    static int totalSize = 0;
	
	 
	    public static void main(String[] args) {
	
	        Scanner scanner = new Scanner(System.in);
	        System.out.print("디렉터리: ");
	        String dirName = scanner.nextLine();
	
	        File dir = new File(dirName);
	
	        if (!dir.exists()||!dir.isDirectory()) {
	            System.out.println("유효하지 않은 디렉터리입니다.");
	            System.exit(-1);
	        }
	
	        countFiles(dir);
	        
	        System.out.println();
	        System.out.println("총 " + totalFiles + "개의 파일");
	        System.out.println("총 " + totalDirs + "개의 디렉터리");
	        System.out.println("크기 " + totalSize + " bytes");
	    }
	
	    public static void countFiles(File dir) {
	
	/*
        * 아래의 로직에 맞게 코드를 작성하시오.
        * 1. dir의 파일 목록(File[])을 얻어온다.
        * 2. 얻어온 파일 목록의 파일 중에서
        *     1) 디렉터리이면 totalDirs를 증가시키고 countFiles()를 재귀호출한다.
        *     2) 파일이면, totalFiels를 증가시키고 파일의 크기를 totalSize에 더한다.
  */
	        	}
	        }
	    }
	}
```


```
실행 결과
___
디렉터리: c:\users\mmlee\documents

총 11158개의 파일
총 1996개의 디렉터리
크기 1999816498 bytes

```


<br>
<br>

## 문제 풀이
  ___
  이번 문제는 주어진 코드에 지시한 부분만 채워넣어주면 되기 때문에.<br>
  따로 설명없이 바로 문제를 풀어보도록 하겠다.<br>
  디렉터리인지 판단하는 `isDirectory()` 와 파일인지 판단하는 `isFile()`만 알면 간단히 풀 수 있다.
  <br> 
  

```js
// file: `DirectoryInfo.java`
import java.io.File;
import java.util.Scanner;

	public class DirectoryInfo {
	
	    static int totalFiles = 0;
	    static int totalDirs = 0;
	    static int totalSize = 0;
	
	 
	    public static void main(String[] args) {
	
	        Scanner scanner = new Scanner(System.in);
	        System.out.print("디렉터리: ");
	        String dirName = scanner.nextLine();
	
	        File dir = new File(dirName);
	
	        if (!dir.exists()||!dir.isDirectory()) {
	            System.out.println("유효하지 않은 디렉터리입니다.");
	            System.exit(-1);
	        }
	
	        countFiles(dir);
	        
	        System.out.println();
	        System.out.println("총 " + totalFiles + "개의 파일");
	        System.out.println("총 " + totalDirs + "개의 디렉터리");
	        System.out.println("크기 " + totalSize + " bytes");
	    }
	
	    public static void countFiles(File dir) {
	
	        File[] files = dir.listFiles();
	        
	        for(int i=0;i<files.length;i++) {
	        	if(files[i].isDirectory()) {
	        		totalDirs++;
	        		countFiles(files[i]);
	        	}else if(files[i].isFile()) {
	        		totalFiles++;
	        		totalSize += files[i].length();
	        	}
	        }
	    }
	}
```
  이를 실행을 해보면 문제가 요구한 실행 결과처럼 뜰 것이다. :)
  <br>
  
