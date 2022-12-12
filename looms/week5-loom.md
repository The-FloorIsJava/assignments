# JavaScript, Important JS for React

# REMINDER: You must record your screen as well with this prompt on the foreground.

[Here is the link for the survey to be completed after.](https://forms.office.com/r/2ty04ksdbs)

# Prompt 1

1. What is HTML?

2. What's the minimum requirements for a HTML file? Explain what each element is for

3. What is an inline vs block element? Give some examples

4. What can you tell me about CSS? How is CSS applied?

5. What is the specificity of applying CSS? 

# Prompt 2

1. What is JavaScript and how does it compare to Java?

2. What are the primitives in JavaScript? Are all of these usable as valid JSON?

3. What is a function in JavaScript? Can you name and differentiate the various types of functions?

4. What is the DOM? How do we manipulate it?

5. What is fetch? why is it important?

# Prompt 3

Explain the following code. Line-by-line. **_NOTE_** Answer some of the comments.

```javascript
// Why bother with this url variable?
let url = "http://localhost:8080"; 

// What's the async and await keywords handling for us?
async function findAll() {
    try {
        const response = await fetch(`${url}/member`);
        // Why must we await the json() invocation?
        const members = await response.json(); 
        formatMultiTable(members); // What's this?
    } catch (error) {
        console.error(error);
    }
}

// Why bother with this function?
function formatMultiTable(members) {
    // Why are we making html into a string?
    let html_code = "";

    // What does the line below tell you members must be?
    const letsSee = members.map((e) => {
        html_code += "<tr>";
        for (const key in e) {
            html_code += `<td>${e[key]}</td>`;
        }
        html_code += "</tr>";
        return html_code;
    });

    // What's happening here? Hint: HTML below
    document.getElementById("memberBody").innerHTML = html_code;
}

```

# Explain the HTML

```html
<div id="nav"></div>
<button onclick="findAll()">Show All Members</button>
<table class="member">
    <thead class="member">
        <tr class="member">
            <th>Member ID</th>
            <th>Full Name</th>
            <th>Email</th>
            <th>Experience in Months</th>
        </tr>
    </thead>
    <tbody id="memberBody" class="member"></tbody>
</table>
```

# Explain briefly how the CSS affects the above tag

```css
button {
    color: rgb(220, 57, 76);
    background-color: rgb(29, 28, 28);
    font-size: 32px;
}

#memberBody {
    font-size: 42px;
    border: 2px solid black;
    padding: 8px;
}

.member {
    padding: 2px;
    border: 3px solid red;
    color: red;
}
```
