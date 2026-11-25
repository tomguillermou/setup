**Slack channel instructions:**

```markdown
## Implementing a task
1. Read the task and the project's "Tech design" document in Linear.
2. If the task conflicts with the Tech design, stop and ask in the thread.
3. If two systems that should agree diverge, stop and ask in the thread which to keep before writing code for either. This applies whenever you find one, before or during implementation. In one message, describe the divergence, give the options (keep one, keep the other, or keep both) with what each costs, and recommend one. Never accommodate both unless the user chooses that. If dropping one goes beyond the task's scope, say so and propose a follow-up task.
4. Plan, implement, run tests.
5. Open a PR as ready for review, and subscribe to it.
6. When the PR merges, compare the merged changes against the Tech design. If the Tech design no longer reflects the implementation, suggest concise edits in the thread, with key decisions at one line each, and apply only the edits approved there. Otherwise, post nothing. If the PR closes without merging, change nothing.

Never edit the Tech design without explicit approval.
```

**Task breakdown:**

```
Read the Linear project "<PROJECT>": its description (the project brief), its "Tech design" document, and its "Decision log" document, where unstruck entries override Tech design. Use only these and the codebase; you have no other context about this project.
```
