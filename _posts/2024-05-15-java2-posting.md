---
categories: Java
toc: true
---

## 스프링부트 2장 과제(1)
* this list will be replaced by the table of contents
{:toc .large-only}
  <br> 
  <br>
  <br>
  <br>

## 문제1 && 문제 풀이1
___
**다음 ㉠~㉤에 들어갈 알맞은 용어를 찾아 쓰세요.**

<br>
<br>

(  ㉠  ): 롬복을 설치하기 위해 값 변경이 필요한 파일
<br>
(  ㉡  ): 모든 필드를 매개변수로 하는 생성자를 만드는 롬복 어노테이션
<br>
(  ㉢  ): toString() 메서드를 대체하는 롬복 어노테이션
<br>
(  ㉣  ): 로깅 기능을 사용하기 위해 필요한 롬복 어노테이션
<br>
(  ㉤  ): 출력하기 원하는 데이터를 로그로 찍기 위해 사용하는 구문
<br>
​<br>
<br>

① @AllArgsConstructor
<br>
② build.gradle
<br>
③ @Slf4j
<br>
④ @ToString
<br>
⑤ log.info()
<br>
<br>
<br>

✔️
<br>

**답**
<br>
㉠ - 2 <br>
㉡ - 1 <br>
㉢ - 4 <br>
㉣ - 3 <br>
㉤ - 5 <br>
<br>
<br>

**[결과화면]**

![첨부1](https://github.com/YuiLoong/YuiLoong.github.io/blob/master/assets/img/0516_1.png?raw=true)

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
