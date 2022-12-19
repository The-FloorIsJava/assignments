# TypeScript/Angular

# REMINDER: You must record your screen as well with this prompt on the foreground.

[Here is the link for the survey to be completed after.](https://forms.office.com/r/2ty04ksdbs)

# Prompt 1

1. What is TypeScript? Why bother with it?

2. What's a decorator in typescript?

3. What makes something a Single Page Application?

4. What is Angular? What are it's advantages over other frameworks & libraries?

5. What's Angular CLI?

# Prompt 2

1. How do we incorporate routing into Angular? How do we set up the routes?

2. What types of Data Binding are there in Angular?

3. What's @Component?

4. What are directives inside of angular? How do they help?

5. What is Karma & Jasmine?

# Prompt 3

Explain the following code. Line-by-line. **_NOTE_** Answer some of the comments.

```typescript
// What's going on with this @?
@Component({
  selector: 'app-members',
  templateUrl: './members.component.html',
  styleUrls: ['./members.component.css']
})
export class MembersComponent implements OnInit {

  members:Member[] = []; // Do we need an empty array here?

  constructor(private memberService:MemberService) { } // What's happening here?

  // What's the purpose for this function?
  ngOnInit(): void {
  }

  // What type of function is this? Does it follow any design pattern?
  findMembers(){
    this.memberService.findAllMembers().subscribe({
      // What's next and what's error?
      next: (data) =>{
        this.members = data as Member[];
      },
      error: (error) =>{
        console.error(error)
      }
    })
  }

}

```

```html
<!-- What types of data-binding are heppning below? -->
<button mat-raised-button color="primary" (click)="findMembers()">Find Members</button>

<!-- What's this div handling for us? -->
<div *ngFor="let member of members">
    <!-- What's being given to our member card? -->
    <app-member-card [member]="member"></app-member-card>
</div>
```

