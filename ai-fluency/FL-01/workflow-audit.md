# FL-01 — AI Workflow Audit and Tool Setup

**Hisham Sabry · General AI Fluency · Week 1**  
**Audit date:** 11 September 2026

## Workflow audit

This audit reflects my current week as a Machine Learning intern building, validating, documenting, and presenting portfolio work. The classification describes the role I want AI to play—not whether AI is technically capable of doing more.

| # | Recurring task | Classification | Why this boundary fits |
|---:|---|---|---|
| 1 | Read a FlyRank assignment and turn it into a checklist | **Collaborate with AI** | AI can surface requirements and ambiguities; I confirm the scope and final interpretation. |
| 2 | Plan the week's internship work and learning blocks | **Delegate to AI with review** | AI can draft a realistic sequence from deadlines and dependencies, but I adjust it to my actual time and energy. |
| 3 | Frame an ML question, target, baseline, and evaluation metric | **Collaborate with AI** | AI is useful for alternatives and failure modes; I decide what question is meaningful and defensible. |
| 4 | Run notebooks and diagnose errors | **Collaborate with AI** | AI can inspect full errors and propose root causes; I rerun the notebook and verify the fix. |
| 5 | Check data quality, split logic, and leakage risks | **Delegate to AI with review** | AI can apply a repeatable checklist, while I review assumptions and approve any data decision. |
| 6 | Execute routine tests, formatting, and notebook validation | **Fully automate** | These deterministic checks should run the same way every time and report failures without hiding them. |
| 7 | Interpret metrics and approve the claims attached to my work | **Just me** | I remain accountable for meaning, uncertainty, limitations, and whether a public claim is honest. |
| 8 | Draft technical documentation and verification steps | **Delegate to AI with review** | AI can produce a structured first draft; I test every instruction and correct the explanation. |
| 9 | Maintain Git branches, commits, and pull-request summaries | **Delegate to AI with review** | The mechanics are repeatable, but I review the diff and destination before anything is published. |
| 10 | Turn a finished project into a concise portfolio case study | **Collaborate with AI** | AI helps with structure and clarity; I supply the evidence, select the story, and remove overclaims. |
| 11 | Improve LinkedIn and GitHub presentation | **Collaborate with AI** | AI can critique clarity and consistency, while the final professional identity and voice must remain mine. |
| 12 | Choose roles to pursue and decide what I want from my career | **Just me** | These choices depend on my interests, values, constraints, and willingness to make the trade-offs. |
| 13 | Summarize course modules into revision notes | **Delegate to AI with review** | AI can organize notes, but I compare them with the source and add what changed my understanding. |
| 14 | Track assignment status and missing evidence | **Fully automate** | A checklist can reliably flag missing links, screenshots, tests, and submission fields. |
| 15 | Prepare for interviews by practicing explanations of my projects | **Collaborate with AI** | AI can challenge me with follow-ups, but I must explain the work accurately in my own words. |

## Three target tasks for FL-02 through FL-04

These are the three recurring tasks I will use when testing prompts, comparing approaches, and designing an automation workflow.

### 1. Convert an assignment brief into an execution checklist

**Done well means:** the checklist captures every deliverable and pass/revise criterion; distinguishes research, implementation, verification, and submission; identifies blockers without inventing requirements; and can be reviewed in under five minutes. A final cross-check must show zero uncovered acceptance criteria.

### 2. Diagnose a failing notebook or validation run

**Done well means:** the full error and relevant context are preserved; the root cause is stated separately from the symptom; the smallest safe fix is applied; no warning or test is hidden; and the notebook runs top to bottom twice with the same fixed seed and materially identical reported metrics.

### 3. Turn verified ML results into a public project summary

**Done well means:** a 150–200 word summary states the problem, data boundary, method, baseline, two verified metrics, and one genuine limitation; contains no private client information; uses measured rather than causal language; and every numerical claim traces to a saved output.

## Toolkit and evidence

| Tool | Intended use | Verification evidence |
|---|---|---|
| ChatGPT / Codex | Planning, coding assistance, review, and validation | Active workspace used to create and verify this audit. |
| Claude Project | A reusable project context with identity, tone, goals, and safety boundaries | **Configured and verified:** “Hisham — AI Fluency Workspace,” with the custom instructions included in this package. |
| Anthropic Academy | *AI Fluency: Framework & Foundations* | **Enrolled and verified:** “Introduction to AI Fluency” is recorded as completed. |

Evidence screenshots are included with the private FlyRank submission so account-specific learning information does not need to be published in the repository.

## Reflection

The main lesson from this audit is that speed is not the same as delegation. I can automate deterministic checks and drafting steps, but the high-consequence boundaries—career choices, interpretation, evidence, and public claims—stay with me. For collaborative tasks, the reliable pattern is: provide context, ask for a concrete artifact, inspect the output, verify it against evidence, and keep responsibility for the final decision.
