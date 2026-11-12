# Course Syllabus

## AI Engineering Apps, IEOR E4577 section 005

Columbia University, 2026 edition.

**Instructor:** Ciro Greco

**Contact:** [cg3631@columbia.edu](mailto:cg3631@columbia.edu)
**GitHub handle:** ciro-greco

**Teaching assistant:** Vinod Badrinarayanan
**Contact:** [vb2680@columbia.edu](mailto:vb2680@columbia.edu)
**GitHub handle:** thevoid12

---

## Course Overview

An applied overview of Artificial Intelligence (AI) with an emphasis on real-world industry use cases, deployment practices and tool chain. The course focuses on building LLM-powered applications: choosing models, engineering context, evaluating systems, and shipping agents that take actions.

This course provides an introduction and hands-on experience with modern AI engineering practices. Students work with real models and real infrastructure, and learn the techniques currently used in industry.

The internet is full of very good learning materials about AI and machine learning. What is usually hard to find is real-world case studies from practitioners who build AI systems daily, and that is what we hope to bring with this course.

---

## Main themes

The course is structured around 7 weeks: 6 weeks of lectures, and 1 final demo day for students, organized in teams, to present an end-to-end AI engineering project. Main topics, roughly in order of appearance:

- **Introduction to AI engineering:** the shift from model-centric to application-centric AI development, and what the job actually involves.
- **Models and inference:** how to choose a model for a task, and how to reason about what it costs to run.
- **Evaluation:** building evals, measuring quality and consistency, and treating the eval set as the product specification.
- **Context and retrieval:** context engineering, retrieval, and memory.
- **Agents:** tool use, MCP, multi-step task execution, permissions, and production failure modes.
- **Building a business on AI products:** problem selection, pricing, moats, go-to-market, and the job market.
- **Team project:** building a functional AI-powered MVP from concept to deployment.

Some lectures use a running example: an agent that handles ecommerce returns. It appears when it helps explain a concept. Other examples appear when they fit better.

**Important Note:** these materials cannot replace the classroom experience, where real learning happens through discussion, collaboration and direct mentorship. The AI field moves fast, so this course is updated every year to reflect current practice.

---

## Course Information

**Title:** AI Engineering Apps
**Term:** 7 weeks
**Hours:** 18

---

## Requirements

**Prerequisites:** undergraduate-level understanding of probability, linear algebra, and Python programming.

### What you need

Everything runs on a normal laptop. You do **not** need GPU hardware, and you will not download or train
model weights. Every model in this course runs on somebody else's infrastructure and you reach it over an API.

**The stack is Google Cloud.** You call hosted models through **Vertex AI** using the Google Gen AI Python
SDK. Google Cloud credits are provided for the course, so there is no cost to you. What you install locally is
Python, Git, the Google Cloud CLI, and a short list of client libraries. No PyTorch, no CUDA, no local
inference.

You will need a GitHub account. The capstone is submitted as a repository, and your team's work lives there
from Week 2 onward.

### Week 1: Environment Setup

1. Set up a GitHub account
2. Install Python 3.11 or later, and Git
3. Install the Google Cloud CLI (`gcloud`)
4. Redeem your Google Cloud credits, select your course project, and enable the Vertex AI API
5. Authenticate, then create a virtual environment and install the course requirements
6. Run the provided setup script. It makes one real model call and prints the response
7. Once your team has formed, create the team repository and add all members plus the instructors as collaborators

Step-by-step instructions are covered in Week 1. If you cannot get access working before Week 2, pair with
a teammate who can and come to office hours.

---

## Course Schedule


| Lesson   | Title                              | Date & Time                     |
| -------- | ---------------------------------- | ------------------------------- |
| Lesson 1 | Introduction to AI engineering     | Sat Oct 31, 11:00 AM to 1:30 PM |
| Lesson 2 | Models and inference               | Sat Nov 7, 11:00 AM to 1:30 PM  |
| Lesson 3 | Evaluation                         | Sat Nov 14, 11:00 AM to 1:30 PM |
| Lesson 4 | Context and retrieval              | Sat Nov 21, 11:00 AM to 1:30 PM |
| Lesson 5 | Agents                             | Sat Dec 5, 11:00 AM to 1:30 PM  |
| Lesson 6 | Building a business on AI products | Fri Dec 11 TBC                  |
| Lesson 7 | Demo Day (final class)*            | Sat Dec 12, 11:00 AM to 1:30 PM |

\* *Live team demos and presentations. Presentation length determined by the final number of teams.*

Guest speakers: TBD

---

## Capstone: what to do, and by when

You will build one AI application, in a team of 3 to 5, over seven weeks. It is submitted as a GitHub
repository. There are no other assignments.

There are four dates.


| Week  | What is due                      |
| ----- | -------------------------------- |
| **1** | Your team                        |
| **2** | Project proposal                 |
| **5** | First version of your repository |
| **7** | Final repository, and your demo  |

---

## Week 1: Form your team

Teams form in Week 1. Three to five members.

Create your GitHub repository and add every team member and the instructors as collaborators.

---

## Week 2: Project proposal

**Two to three pages at most**, submitted by the end of the week.

The required structure (seven sections, with the length expected for each) is in
[`capstone_proposal_template.md`](capstone_proposal_template.md). Follow it in order.

Your idea will have a weight in the final grade. If your idea needs reshaping, you and the instructor work it out
between Weeks 2 and 3. **By the end of Week 3 every team has a project it can build.**

---

## Week 5: First version of your repository

Push what you have and tell us it is there. This is a checkpoint, not a submission: it is reviewed, and you
get feedback, and it does not affect your grade.

What needs to be in the repository:

1. **Code that kind of runs.** One path working end to end is enough. It does not need to be the final design.
2. **A README** saying what the project is, how to run it, and what currently works.
3. **A short status note**, half a page. What is done, what is next, and anything that is blocking you.

Being behind at Week 5 does not affect your grade. It does leave the instructors less time to help before the final submission.

---

## Week 7: Final submission and Demo Day

Your deliverables are due on Demo Day. What to submit and how is in
[`capstone_submission_instructions.md`](capstone_submission_instructions.md).

### On the day

Each team gives a live demo and a short presentation of roughly **7 minutes**, followed by up to **10 minutes**
of discussion. Exact length is set once the number of teams is known. All team members take part.

The demo must run end to end, from the code in your repository.

### How it is graded


| Weight  | Area                                 | What we look for                                                                                                                                                                                                                                                                                                                        |
| ------- | ------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **10%** | Idea                                 | Does it solve a problem worth solving? Does it have potential for a business application?                                                                                                                                                                                                                                               |
| **30%** | Functionality and reliability        | Does it solve the problem you stated? Does it run repeatably, from a clean checkout, on inputs it was not tuned against?                                                                                                                                                                                                                |
| **30%** | Technical approach and rigor         | Two halves, scored evenly. **Design:** are your model choice, context design, retrieval, tool surface and cost decisions sound, and can you defend them? **Measurement:** is there a real eval set that represents the task rather than the happy path? Did measurement change a decision you made? Do you know where your system fails? |
| **20%** | Product thinking and user experience | Is there a clear user story? Is the scope right? Would the intended user actually use this? Is there a plausible account of who would pay for it?                                                                                                                                                                                       |
| **10%** | Communication and teamwork           | Quality of the demo, deck and written materials. Evidence of collaborative work and clear ownership, git history included.                                                                                                                                                                                                              |
