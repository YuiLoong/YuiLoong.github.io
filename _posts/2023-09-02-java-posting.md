## 자바 컬렉션 프레임워크
**컬렉션 프레임워크** 를 요즘 공부하고 있는 중인데 생각보다 많다...
  그렇지만, c언어 자료구조를 공부하고보니 알면 알수록 정말 재밌는 파트인 것 같아서 시간이 금방간다.
  그래서 재밌다고 느껴질 때! 문제를 풀어볼까한다. :)
  
## 문제
___
+ BoardDao 객체의 getBoardList ( ) 메소드를 호출하면 List<Board> 타입의 컬렉션을 리턴함. 
  ListExample 클래스의 실행 결과를 보고, BoardDao 클래스와 getBoardList ( ) 메소드를 작성하기
  
```js
// file: `Board.js`
class Board {
    private String title;
    private String content;
    
    public Board(String title, String content) {
        this.title = title;
        this.content = content;
    }
    public String getTitle() { return title; }
    public String getContent() {return content;}
}
```
```js
// file: `ListExample.js`
import java.util.List;

public class ListExample {
    public static void main(String[] args) {
        BoardDao dao = new BoardDao();
        List<Board> list = dao.getBoardList();
        for(Board board : list) {
          System.out.println(board.getTitle() + "-" + board.getContent());
        }
    }
}
```
```
실행 결과
___
제목1-내용1
제목2-내용2
제목3-내용3
```

## 문제 풀이
<br>
  ---
  `ArrayList`는 List 컬렉션에서 자주 보이는 컬렉션이다.
  그만큼 자주 사용하며, 간단한 특징을 써보자면

  >1.제한 없이 객체를 추가할 수 있다.<br>
>2.객체 추가시, 내부 배열에 객체가 저장된다
    

  삽입/삭제가 자주 필요한 문제가 아니기 떄문에 굳이 `LinkedList`를 쓸 필요가 없어 보이기에
  ArrayList를 사용하여 문제를 접근해보겠다.

  우선, `BoardDao 클래스` 와 `getBoardList 메소드` 작성을 하고
    
```js
// file: `BoardDao.js`
class BoardDao{
	public List<Board> getBoardList(){
		
	}
}
```
  다음으로 ArrayList 컬렉션을 생성하는데, 생성은 이렇게 할 수 있다.
  > List<예시> list = new ArrayList<예시> ();
> <br>
  > List<예시> list = new ArrayList<>();

  재밌는 점은 뒤에 `예시` 부분을 생략할 수 있다는 것이다. 
  어떻게 쓰든 둘 다 <span style="color:#2D3748;background-color:#fff5b1;">`예시`에 지정된 타입의 객체만 저장</span> 이라는 것이다.

  물론 주의할 점이 있다.
  > List list = new ArrayList();
  <br>
 경우는 <span style="color:red">모든 타입의 객체를 저장</span> 한다는 점!

  
  <br>
  이렇게 생성 방법을 간단하게 알아봤다. 이제 이를 이용해서 적용을 해보자.

  ```js
// file: `BoardDao.js`
import java.util.ArrayList;
class BoardDao{
	public List<Board> getBoardList(){
		List<Board> list = new ArrayList<Board>();
		list.add(new Board("제목1","내용1"));
		list.add(new Board("제목2","내용2"));
		list.add(new Board("제목3","내용3"));
		
		return list;
	}
}

```

  add 메서드를 이용해서 ArrayList에 객체를 추가해 보았다. 
  이를 실행을 해보면 문제가 요구한 실행 결과처럼 뜰 것이다. :)
