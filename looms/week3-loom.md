# Project, REST & OOP

# REMINDER: Each prompt is answerable in 5min. You'll have 25 minutes to respond to each of these questions. You must record your screen as well with this prompt on the foreground.

[Here is the link for the survey to be completed after.](https://forms.office.com/r/2ty04ksdbs)

# Prompt 1
1. What is REST?

2. What are the 4 pillars of OOP?

3. What is a HashMap? How does it compare to HashTable?

4. What are queue's in Java?

5. What is time complexity?

# Prompt 2

1. Tell me about your project. Make sure to answer the questions below.

    - What pillars of OOP are you using in your project?
    - What REST principles are you adhering to? What aren't you adhering to?
    - How did you establish a connection between your API & Database?
    - How does you API handle any issues that may occur while running?
    - What's your biggest weakness from this project? How will you solve for the next?

# Prompt 3

Explain the following code. Line-by-line. **_NOTE_** Answer the comments.

```java
// What conceptual practices are occuring here?
public class Application {
    public static void main(String[] args) {

        Javalin app = Javalin.create().start(8080);
        MemberService memberService = new MemberService(new MemberDAO());

        // How does the the line below differ from the last two lines in the main method?
        new MemberController(app, memberService).memberEndpoint(); 

        BankAccountController bankAccountController = new BankAccountController(memberService);
        bankAccountController.bankAccountEndpoint(app);
    }
}
```

```java
// What conceptual practices are occuring here? How does each line work?
public class InvalidMemberInputException extends RuntimeException{

    public IMIException(String message) {
        super(message);
    }
}
```

```java
// Based on the endpoints, what can this application do? What conceptual practice or principle is this following?
public void memberEndpoint(){
        app.get("hello", this::helloHandler);
        app.post("member",this::postMemberHandler);
        app.put("member", this::memberUpdateHandler);
        app.delete("member/{id}", this::deleteByIdHandler);

        app.get("bankAccount/{member}", this::findAccountsHandler);
        app.put("withdrawal", this::withdrawalHandler);
    }
```
