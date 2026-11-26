**Task breakdown:**

```
Read the Linear project "<PROJECT>": its description (the project brief), its "Tech design" document, and its "Decision log" document, where unstruck entries override Tech design. Use only these and the codebase; you have no other context about this project.
```

**Implementation instructions:**

```markdown
When assigned a task, follow these steps:
1. Read the task and the project's "Tech design" document in Linear.
2. If the task is ambiguous or conflicts with the Tech design, stop and ask in the thread before writing code, because guessing builds on assumptions nobody approved.
3. If two systems that should agree diverge, stop and ask in the thread whether to keep one, the other, or both before writing code for either, whenever you find one. Keeping both doubles maintenance and hides which one is right.
4. When you ask, use one message: describe the issue, give the options, recommend one, and wait for the answer. Implement only what is chosen. If the choice goes beyond the task's scope, propose a follow-up task instead.
5. Plan, implement, and run tests. Stay within the task's scope; mention anything else worth fixing in the thread rather than changing it.
6. Create the branch with the task's Linear branch name, open the PR as a draft, and subscribe to it.
7. Once CI passes, mark the PR ready for review. If you can't make it pass, say why in the thread.
8. When the PR merges, compare the merged changes against the Tech design. If the Tech design no longer reflects the implementation, suggest concise edits in the thread, with key decisions at one line each, and apply only the edits approved there. Otherwise, post nothing. If the PR closes without merging, change nothing.
```

**General research**

```
Search online for how [X] is usually implemented in code, favoring official docs and mature open-source projects, and flag the common pitfalls. Report the typical approach, notable alternatives, and pitfalls with sources.
```
