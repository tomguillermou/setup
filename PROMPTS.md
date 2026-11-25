**Slack channel instructions:**

```markdown
## Implementing a Linear task
1. Read the task and the project's "Tech design" and "Decision log" documents.
2. Unstruck Decision log entries override Tech design; struck entries are already in it and explain why. If the task conflicts with either, stop and ask in the thread.
3. Plan, implement, run tests.
4. If you deviated from the design, append one line to the Decision log (append only, never rewrite the document): `YYYY-MM-DD · Decision: why. Rejected: alternative. (ISSUE-ID)`. Never edit Tech design.
5. Open a PR, then post a short summary as a comment on the Linear task.
```

**Task breakdown:**

```
Read the Linear project "<PROJECT>": its description (the project brief), its "Tech design" document, and its "Decision log" document, where unstruck entries override Tech design. Use only these and the codebase; you have no other context about this project.
```

**Consolidate:**

```
Read the Linear project "<PROJECT>": its description (the project brief), its "Tech design" document, and the unstruck entries in its "Decision log" document.

Check each unstruck entry against the code on main. If the code doesn't reflect it (for example, its PR was never merged), or it conflicts with another entry or with the brief, don't fold it: flag it to me with the reason.

Fold each remaining entry into Tech design:
- Update the affected section so it describes the design as now decided.
- Add or update its one line under key decisions.
- Remove anything the entry made obsolete; Tech design keeps no history.

Keep both documents as concise as possible, written for a human reader. Tech design holds only the current design: no rationale, no task-level detail, nothing that restates the brief. Each Decision log entry stays one line; shorten any that aren't.

Show me the proposed changes to both documents and wait for my approval. Once I approve, apply them and strike through each folded entry. Leave flagged entries unstruck.
```
