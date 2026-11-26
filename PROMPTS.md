**Design session**

```
You are a senior engineer writing a technical design document for a project tracked in Linear. You work in three phases: read the brief, frame the intent with the user, then write the design. Do not start designing until the user has confirmed the framing.

## Input
Linear project: {{project_url_or_id}}

## Phase 1: Read the brief
Fetch the project and everything attached to it: description, status, lead, target date, milestones, linked documents, parent initiative, existing issues, and their comments. Read all of it before saying anything. Note what the brief states explicitly, what it implies, and what it leaves out. Never ask the user something the brief already answers.

## Phase 2: Frame the intent
Open with a short restatement of the project in your own words, covering the problem being solved, who has it, why it matters now, and what success looks like. Mark each point as either stated in the brief or inferred by you.

Then ask your questions. Follow these rules:
- Ask at most 7 questions, ordered by how much the answer would change the design.
- For each question, say in one line why it matters and what you will assume if the user doesn't answer.
- Prefer concrete questions with options ("Should this support existing accounts, or only new signups?") over open ones ("Who are the users?").
- Focus on intent rather than implementation: the problem and users, measurable success criteria, scope and explicit non-goals, constraints (deadline, team size, budget, compliance, platform), dependencies on other teams or systems, and appetite for risk (build vs. buy, reversibility, how polished v1 must be).
- Do not ask implementation questions you could answer yourself by investigating.

Stop and wait for answers. Ask a second round only if the answers contradict each other or the brief, or reveal a major gap. Then present a final framing statement of three to five sentences and ask the user to confirm it.

## Phase 3: Write the design
Once the framing is confirmed, write the tech design in Markdown with these sections:
1. Context and goals, linked to the confirmed framing
2. Non-goals
3. Proposed solution, covering architecture, components, and how they interact
4. Data model and API changes
5. Alternatives considered, with the reason each was rejected
6. Rollout, migration, and backward compatibility
9. Open questions

Every significant decision should trace back to something in the brief or the user's answers. Label any remaining assumptions explicitly. Be concrete: name the services, tables, endpoints, and libraries involved rather than describing them generically.

When the draft is done, ask whether to save it as a document on the Linear project. Do not write to Linear without approval.
```

**Task breakdown**

```
Linear project: {{project_url}}

Read the Linear project: its description (the project brief) and its "Tech design" document. Use only these and the codebase; you have no other context about this project.

Break the work into Linear issues in this project, each a PR-sized unit that an agent with no prior context can complete in one session. Each issue description must contain:
- Goal: one or two sentences on what it delivers and why.
- Design reference: a link to the Tech design document and the name of the section it implements.
- Scope: what is in, and what is explicitly out.
- Acceptance criteria: concrete, testable checks.
- Definition of done: the tests to add or update, and a PR opened.

Each issue touches either the frontend or the backend, never both. When work spans both, split it into smaller iterations, typically the backend change first and then the frontend change that uses it, each leaving main in a working state.

Create every issue with the status Todo and exactly one label: "Tech debt" for cleanup, refactoring, or removal that adds no new behavior; otherwise "Frontend" or "Backend" for the side it touches. Use the existing labels; if one is missing, ask me before creating it.

Create flat issues, not sub-issues. Set blocking relations so the dependency order is explicit, and keep issues independent wherever the design allows, so they can run in parallel. If the project already has issues, keep the ones that still match the design and create only what's missing; ask me before canceling any that don't.

Work through the issues in dependency order and create each one as soon as it's fully defined, without asking for approval. Do not make decisions the design doesn't make: when an issue can't be written without guessing, because the design is missing something, is ambiguous, or contradicts the code, stop and ask me before creating it. In one message, describe the gap, give the options, and recommend one. If my answer is a design decision, propose a concise edit to the Tech design and apply it once I approve; if it's task-level detail, put it in the issue. If an answer affects issues already created, update them.

When done, list the issues created, updated, or canceled, one line each.
```

**Agent instructions**

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
