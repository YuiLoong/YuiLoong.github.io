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

## 문제2 && 문제 풀이2
___
**2. 다음 ㉠에 들어갈 용어를 쓰세요.**
<br>
(  ㉠  )(이)란 JPA의 CrudRepository가 제공하는 메서드로, 특정 엔티티를 모두 가져와 Iterable 타입으로 반환합니다.
<br>
<br>
<br>

✔️
<br>

**답**
<br>
㉠ - findAll()
<br>
<br>

## 문제3 && 문제 풀이3
___
**4장 셀프체크에서 만든 MemberController에서 회원 조회(특정회원 조회, 전체 회원 조회)가 되도록 구현하기**
<br>
수정이나 생성이 필요한 파일들
<br>

> 컨트롤러: controller/MemberController.java <br>
> 리파지터리: repository/MemberRepository.java <br>
> 뷰템플릿: templates/members/show.mustache, templates/members/index.mustache <br>


<br>
<br>

✔️
<br>

**답**
<br>

```js

//file: MemberController.java
@Slf4j
@Controller
public class MemberController {
    private static final Logger log = LoggerFactory.getLogger(MemberController.class);
    @Autowired
    private MemberRepository memberRepository;

    @GetMapping("/signup")
    public String newMemberForm() {
        return "members/new";
    }

    @PostMapping("/join")
    public String createMember(MemberForm form) {
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

    @GetMapping("/members/{id}")
    public String show(@PathVariable Long id, Model model) {

        Member memberEntity = memberRepository.findById(id).orElse(null);

        model.addAttribute("member", memberEntity);
        return "members/show";
    }

    @GetMapping("/member")
    public String index(Model model) {
        List<Member> memberEntityList = (List<Member>) memberRepository.findAll();

        model.addAttribute("memberList", memberEntityList);
        return "members/index";
    }
    
}
```
<br>

```js

//file: MemberRepository
public interface MemberRepository extends CrudRepository<Member, Long> {
    @Override
    ArrayList<Member> findAll();
}
```
<br>

```js

//file: show.mustache
{{>layouts/header}}

<table class="table">
    <thead>
    <tr>
        <th scope="col">Id</th>
        <th scope="col">email</th>
        <th scope="col">password</th>
    </tr>
    </thead>
    <tbody>
    {{#member}}
        <tr>
            <th scope="row">{{id}}</th>
            <td>{{email}}</td>
            <td>{{password}}</td>
        </tr>
    {{/member}}
    </tbody>
</table>

{{>layouts/footer}}
```

<br>

```js

//file: index.mustache

{{>layouts/header}}

<table class="table">
    <thead>
    <tr>
        <th scope="col">Id</th>
        <th scope="col">email</th>
        <th scope="col">password</th>
    </tr>
    </thead>
    <tbody>
    {{#memberList}}
        <tr>
            <th scope="row">{{id}}</th>
            <td>{{email}}</td>
            <td>{{password}}</td>
        </tr>
    {{/memberList}}
    </tbody>
</table>


{{>layouts/footer}}

```

<br>
<br>
<br>



