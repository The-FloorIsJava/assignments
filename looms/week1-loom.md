# Java

# REMINDER: Each prompt is answerable in 5min. You must record your screen as well with this prompt on the foreground.

[Here is the link for the survey to be completed after.](https://forms.office.com/r/2ty04ksdbs)

# Prompt 1

1. Name 3 linux commands and what they do.

2. What git? How does it compare to GitHub?

3. What commands must you run to save any local changes and submit those changes to github.

4. What is the main method signature and why is it important?

5. What are class in java? What three characteristics does a java class contain?

# Prompt 2

1. Name all the methods of handling exceptions.

2. What's the difference between an error, checked exception and an unchecked exception?

3. What are annotations in Java?

4. What is JUnit & TDD?

5. What is SDLC? What forms of SDLC are there and how do they differ?

# Prompt 3

Explain the following code. Line-by-line. **_NOTE_** Answer some of the comments.

```java

public class Member{
    // What are these?
    private email;
    private name;
    private balance;


    // Why have the below code?
    public Member(){}

    public Member(String email, String name, double balance){
        this.email = email;
        this.name = name;
        this.balance = balance;
    }

    // What are the below methods for? Why do we need them?
    public String getEmail(){
        return email;
    }

     public String getName(){
        return name;
    }

     public int getBalance(){
        return balance;
    }

}
```

```java

public class MemberService {

    List<Member> memberList; // what's occuring here? What's the <> with Member inside handling?

    public MemberService(){
        memberList = new ArrayList<>(); // Why do we instantiate the ArrayList here instead of above?
    }

    public boolean isMemberValid(Member newMember){ // Why do we need this method?
        if(newMember == null) return false;
        if(newMember.getEmail() == null || newMember.getEmail().trim().equals("")) return false;
        if(newMember.getName() == null || newMember.getName().trim().equals("")) return false;
        if(newMember.getBalance() < 0 ) return false;
        return true;
    }

    public boolean isEmailAvailable(String email){
        for(Member member: memberList){ // what is this an example of?
            if(member == null) break; // why do we need this?
            if(member.getEmail().equals(email)){ // Why bother checking email?
                return false;
            }
        }
        return true;
    }
}

```

[**_Here is the link for the survey to be completed after._**](https://forms.office.com/r/2ty04ksdbs)
