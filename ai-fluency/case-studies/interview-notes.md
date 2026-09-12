# Case-study interview notes

Claude interviewed me one focused question at a time. These notes preserve the useful answers and
the edits made when a question reached beyond the evidence.

## Case 1 — Search-opportunity ranking

| Question | Evidence-based answer or revision |
|---|---|
| What problem did the project solve? | With 86,574 eligible pages and limited review attention, I evaluated a method for prioritizing a human-review queue. I removed an unsupported story about a broken prior process. |
| Why a random forest? | The repository proves a constrained model specification and comparisons with a transparent rule and constant dummy. It does not preserve a broad model-family search or full contemporaneous selection rationale, so the case does not claim either. |
| Why split by client? | Client is a known grouping variable and the evaluation question concerns clients unseen during training. A 16-client train and six-client holdout enforces that boundary and produces zero client overlap. I removed unsupported guesses about the kinds of within-client similarity. |
| How should the metric tradeoff be explained? | Median client NDCG@20 and MAE improved, but precision@20 fell. The model was better for graded ranking quality and proxy-score error on this holdout, not for top-20 hit rate. More false positives mean more review effort. |
| Why run a deliberate leakage test? | A future field acted as a negative control. Its invalid perfect NDCG showed how leakage could masquerade as success. Rejecting it proves that specific failure mode was detected, not that every possible leak is absent. |
| What does the uncertainty interval prevent me from claiming? | With only six holdout clients, the 0.405–0.876 interval is wide. The result does not establish broad robustness, production readiness, or guaranteed future lift. |
| What is the privacy boundary? | Only aggregate results are public. Client/content hashes are grouping context; URLs, titles, raw queries, identifiers, product-trend fields, and GA4 fields are excluded from public artifacts. |
| What should land in a 30-second skim? | Lead with the rejected perfect score: suspiciously good metrics are failures to investigate, not wins to advertise. Then show the valid grouped-holdout result and its precision tradeoff. |

## Case 2 — Responsible-AI workflow audit

| Question | Evidence-based answer or revision |
|---|---|
| What problem did the audit solve? | I needed a repeatable way to use AI without silently outsourcing judgments that determine whether my work is correct, defensible, or personally mine. I removed “for speed” from the result because no productivity gain was measured. |
| How were the 15 tasks classified? | Four roles: Collaborate with AI, Delegate to AI with review, Fully automate, and Just me. The deciding test was the kind of judgment and verification each task requires. |
| What makes the assignment checklist measurable? | It covers every deliverable and pass/revise criterion, separates work phases, flags blockers without inventing requirements, can be reviewed in under five minutes, and ends with zero uncovered acceptance criteria. |
| What makes notebook diagnosis more than an explanation? | The full error is preserved, cause is separated from symptom, the smallest safe fix is applied, nothing is hidden, and the notebook runs top to bottom twice with a fixed seed and materially identical metrics. An AI explanation remains a hypothesis until reruns verify it. |
| What makes an ML summary traceable? | It is 150–200 words, includes the data boundary, baseline, two verified metrics, and a genuine limitation, and every number matches a saved notebook output or committed metric receipt. |
| What is the limitation? | This is a self-authored operating protocol. It does not prove consistent compliance, productivity improvement, optimal categories, or independent validation. |

## Editorial decisions from the interview

- Separate the core problem from methodological boundaries.
- Lead with a concrete decision, not a personality adjective.
- Put the weaker metric beside the stronger one.
- State what each artifact proves and what it cannot prove.
- Use the repository as the ceiling for every public claim.
