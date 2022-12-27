# Spring, Spring Boot, MVC, DataJPA, AOP

# REMINDER: Each prompt is answerable in 5min. You must record your screen as well with this prompt on the foreground.

[Here is the link for the survey to be completed after.](https://forms.office.com/r/2ty04ksdbs)

# Prompt 1

1. What is Spring?

2. What does a Spring Bean Scope & Lifecycle look like?

3. What ways can we configure Spring projects?

4. In what ways can we inject beans in spring?

5. What is Spring Boot?

# Prompt 2

1. What is Spring Data JPA?

2. What changes about our DAO with the introduction of Spring Data JPA?

3. What is Spring AOP?

4. What is Spring MVC?

5. What is Spring Actuator?

# Prompt 3

Explain the following code. Line-by-line. **_NOTE_** Answer some of the comments.

```java

@RestController // What's this do for us? Any different than a @Controller?
@RequestMapping("/member")
public class MemberController {

    private final MemberService memberService;

    @Autowired // do we need this?
    public MemberController(MemberService memberService){
        this.memberService = memberService;
    }

    @GetMapping
    @Secured(isAdmin = true) // Who provided this? What's it doing?
    public List<MemberResponse> findAll(){
        return memberService.readAll();
    }

    @GetMapping("/{id}") // What's happening with this method?
    public MemberResponse findById(@PathVariable String identifier){
        return memberService.findById(identifier);
    }

    @GetMapping("/query")
    public MemberResponse findByIdQuery(@RequestParam String id){
        return memberService.findById(id);
    }

    @PostMapping
    @ResponseStatus(value = HttpStatus.CREATED) // What's this?
    //What are the @RequestBody & @Valid annotaions proceeding the Parameter definition?
    public MemberResponse register(@RequestBody @Valid NewRegistrationRequest newRegistrationRequest){
        return memberService.registerMember(newRegistrationRequest);
    }

    @PutMapping
    public String update(@RequestBody EditMemberRequest editMemberRequest){
        memberService.update(editMemberRequest);
        return "The update was applied to the member";
    }

    // What's going on here?
    @ExceptionHandler(Exception.class)
    @ResponseStatus(value = HttpStatus.INTERNAL_SERVER_ERROR)
    public @ResponseBody String exception(Exception ex){
        return "Error has occured in our program, please check logs" + ex.getClass().getName() + " with message: " + ex.getMessage();
    }

```

```java

@Repository // What's this providing for us?
public interface MemberRepository extends CrudRepository { // What's missing?
    @Query(value = "from Member where email= :email")
    Optional<Member> checkEmail(String email); // What's the Optional<Member>?

    // What on earth does this method handle for us? How does it work?
    Optional<Member> findByEmailAndPassword(String email, String password);
}

```
