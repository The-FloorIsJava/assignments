# Java, JDBC & Maven

# REMINDER: Each prompt is answerable in 5min. You'll have 25 minutes to respond to each of these questions. You must record your screen as well with this prompt on the foreground.

[Here is the link for the survey to be completed after.](https://forms.office.com/r/2ty04ksdbs)

# Prompt 1

1. What is SQL? Why do we use it?

2. Name some of the sub-languages of SQL and keywords associated with them

3. What is a primary key? How does it compare to a foreign key?

4. Given an employee table in a database, how would you query for any employee with a salary above $50,000 for their name, email, salary and department in order of highest to lowest salary?

5. What is referential integrity?

# Prompt 2

1. What can you tell me about JDBC? Why do we use it?

2. What do we need in order to establish the connection with out database? Why doesn't java provide it?

3. What is the difference between a Statement and PreparedStatement?

4. What is Maven?

5. How do you identify maven artifacts or dependencies? How does Maven provide them?

# Prompt 3

Explain the following code. Line-by-line. **_NOTE_** Answer some of the comments.

```sql
-- What's the follow statement doing? What are some of the key sql features and functions being performed here?
select distinct salary from employee e1 
where 
    2=Select count(distinct salary) from employee e2 
where 
    e1.salary<=e2.salary;


-- What's the follow statement doing? What are some of the key sql features and functions being performed here?
update employee
set
    salary = 50000
where 
    employee_id = d4276cfc-d7d2-41b5-9257-3c2a38862ffc;

```

```java

// What's happening in the line below?
public class MemberDao implements CRUD<Member> {

    @Override
    public Member findById(String id) { // what's the id being provided here for?
        try(Connection conn = ConnectionFactory.getConnectionFactory().getConnection()){ // what's this an example of?
            String sql = "select * from members where email = ?";
            PreparedStatement ps = conn.prepareStatement(sql); 

            // What's the method from ps doing?
            ps.setString(1, id);

            ResultSet rs = ps.executeQuery();

            // Why both with the below code?
            if(!rs.next()){
                throw new InvalidUserInputException("Enter information is incorrect for login, please try agian");
            }

            // What's happening with this method? See below
            return convertSqlToMember(rs);

        } catch (SQLException e){
            e.printStackTrace();
            return null;
        }
    }


    // Explain the reasoning behind each line?
    private Member convertSqlToMember(ResultSet resultSet) throws SQLException{
        Member member = new Member();

        member.setEmail(rs.getString("email"));
        member.setFullName(rs.getString("full_name"));
        member.setExperienceMonths(rs.getInt("experience_months"));
        member.setRegistrationDate(rs.getDate("registration_date"));
        member.setPassword(rs.getString("password"));
    }

    // Are there any missing methods?

}
```
