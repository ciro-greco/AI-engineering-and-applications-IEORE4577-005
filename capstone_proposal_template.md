# Week 2 project proposal: required structure

**AI Engineering Apps, IEOR E4577 section 005, 2026**

Two to three pages at most, seven sections, in this order. Due at the end of Week 2. Copy the template below into your team repository as `PROPOSAL.md`, fill it in, and send the instructor the link.

Write it plainly. Short sentences, concrete nouns, no marketing. A proposal that names one specific user and one specific task is stronger than one that promises a platform.

The idea counts for 10% of the final grade. If it needs reshaping, you and the instructor work it out between Weeks 2 and 3. By the end of Week 3 every team has a project it can build.

---

## What each section asks for

| # | Section | Length | What it must say | Graded later under |
|---|---|---|---|---|
| 1 | Problem | 2 to 3 sentences | Who has the problem, what they do about it today, and what that costs them in time, money or errors | Idea |
| 2 | User | 3 to 4 sentences | Who uses it, who pays for it and why, why they would choose it over what exists today, and what you still need to test | Idea; Product thinking |
| 3 | MVP | 3 to 4 sentences | The smallest version that works end to end: what the user does and what the application does. End with one line on what is not in the MVP | Functionality |
| 4 | Data | 2 sentences | The data you need and where it comes from. If the real data is private, what you will use instead | Technical approach (design) |
| 5 | Models and APIs | 3 to 4 bullets | The models, retrieval or tools you plan to use, and a rough cost per completed task | Technical approach (design) |
| 6 | Evaluation | 2 to 3 sentences, plus targets | What a correct output looks like, the test set you will build and where it comes from, and the targets you will measure | Technical approach (measurement) |
| 7 | Risks | 3 to 4 rows | What is most likely to go wrong, and the fallback for each | Technical approach (design) |

Sections 5 to 7 are a plan. Week 3 (evaluation) will change section 6, and the course material on inference will sharpen the cost in section 5. Revise them in your repository as you learn; the proposal is the starting point of your final product brief.

---

## Template

```markdown
# [Project name]

Team name: [name]

## 1. Problem
[Who has it. What they do today. What it costs them.]

## 2. User
[Who uses it. Who pays and why. Why they would choose it over what exists. What you still need to test.]

## 3. MVP
[What the user does. What the application does.]
Not in the MVP: [what you will not build].

## 4. Data
[The data you need and where it comes from. What you will use instead if the real data is private.]

## 5. Models and APIs
- [Model or models]
- [Retrieval or tools]
- Cost: about $[x] per completed task

## 6. Evaluation
[What a correct output looks like. The test set and where it comes from.]

| Measure | Target |
| --- | --- |
| [Measure] | [Target] |

## 7. Risks

| Risk | Fallback |
| --- | --- |
| [Risk] | [Fallback] |
```
