---
categories: Java
toc: true
---

## 스프링부트 10장 실습(1)
* this list will be replaced by the table of contents
{:toc .large-only}
  <br> 
  <br>
  <br>
  <br>

## 문제1 && 문제 풀이1
___
**1. 다음 ㉠~㉤에 각각 들어갈 용어를 찾아 쓰세요.Permalink**
<br>

(  ㉠  ): REST API 구현을 위한 컨트롤러에 사용하는 어노테이션 <br>
(  ㉡  ): HTTP 요청 중 PATCH 메서드를 처리하는 어노테이션 <br>
(  ㉢  ): HTTP 요청 중 DELETE 메서드를 처리하는 어노테이션 <br>
(  ㉣  ) REST API 요청을 받아 응답할 때 HTTP 상태 코드, 헤더, 본문을 실어 보내는 클래스 <br>
(  ㉤  ): HTTP 상태 코드를 관리하는 클래스 <br>
<br>
<br>

① @DeleteMapping <br>
② ResponseEntity <br> 
③ @RestController <br> 
④ @PatchMapping <br> 
⑤ HttpStatus <br> 

✔️ <br>

㉠ - 3 
<br>
㉡ - 4
<br>
㉢ - 5 
<br>
㉣ - 1
<br>
㉤ - 2

<br>
​<br>
<br>





## 문제2 && 문제 풀이2
___
**1. coffee 데이터를 REST API로 구현해 다음과 같은 결과가 나오도록 구현하기**
<br>
<br>
✔️
<br>

```js
//file: api/CoffeeApiController.java

import java.util.List;

@Slf4j
@RestController
public class CoffeeApiController {
    @Autowired
    private CoffeeRepository coffeeRepository;
    //Get
    @GetMapping("/api/coffees")
    public List<Coffee> index(){return coffeeRepository.findAll();}

}

```
<br>

```js
//file: dto/CoffeeDto.java

@AllArgsConstructor
@ToString
public class CoffeeDto {
    public Long id;
    private String name;
    private String price;

    public Coffee toEntity(){
        return new Coffee(id,name,price);
    }

}
```
<br>

```js
//file: entity/Coffee.java

@ToString
@AllArgsConstructor
@NoArgsConstructor
@Entity
@Getter

public class Coffee {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    @Column
    private String name;
    @Column
    private String price;
    public void patch(Coffee coffee){
        if(coffee.name != null)
            this.name = coffee.name;
        if(coffee.price != null)
            this.price = coffee.price;
    }
}
```
<br>

```js
//file: repository/CoffeeRespository.java

public interface CoffeeRepository extends CrudRepository <Coffee,Long> {
    @Override
    ArrayList<Coffee> findAll();
}
```
<br>

![첨부1](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0613_1.PNG?raw=true)

<br>
<br>



