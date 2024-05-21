---
categories: Java
toc: true
---

## 스프링부트 5장 실습(1)
* this list will be replaced by the table of contents
{:toc .large-only}
  <br> 
  <br>
  <br>
  <br>

## 문제1 && 문제 풀이1
___
**1. 다음 ㉠~㉡에 들어갈 용어를 쓰세요.**

<br>
<br>

(  ㉠  )(이)란 URL 요청으로 들어온 전달값을 컨트롤러의 매개변수로 가져오는 어노테이션입니다.
<br>
(  ㉡  )(이)란 JPA의 CrudRepository가 제공하는 메서드로, 특정 엔티티의 id 값을 기준으로 데이터를 찾아 Optional 타입으로 반환합니다.
<br>
​<br>
<br>

✔️
<br>

**답**
<br>
㉠ - @PathVariable <br>
㉡ - findById() <br>
<br>
<br>
<br>

## 문제2 && 문제 풀이2
___
**3장 셀프체크에서 만든 다음 코드를 롬복으로 리팩터링하기**
<br>
<br>
<br>

✔️
<br>

**답**
<br>

```js
//file: dto/MemberForm.java

@AllArgsConstructor
@ToString
public class MemberForm {
    private String email;
    private String password;
    

    public Member toEntity() {
        return new Member(null, email, password);

    }
}
```

<br>
<br>

```js
//file: controller/MemberController.java

@Slf4j
@Controller
public class MemberController {
    private static final Logger log = LoggerFactory.getLogger(MemberController.class);
    @Autowired
    private MemberRepository memberRepository;
    @GetMapping("/signup")
    public String newMemberForm(){
        return "members/new";
    }

    @PostMapping("/join")
    public String createMember(MemberForm form){
        log.info(form.toString());
//        System.out.println(form.toString());
        //1.DTO를 엔티티로 변환
        Member member = form.toEntity();
        log.info(member.toString());
        //System.out.println(member.toString());

        //2. 리파지터리로 엔티티를 DB에 저장
        Member saved = memberRepository.save(member);
        log.info(saved.toString());
        //System.out.println(saved.toString());
        return "";
    }
}

```
