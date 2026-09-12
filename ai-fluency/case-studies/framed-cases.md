# Work that speaks for itself

## Voice card

**Direct, precise, plain, candid, evidence-first, human.**

## Case 1 — I rejected a perfect score

> A future field gave me a perfect NDCG score, so I rejected the result. Suspiciously good metrics
> are failures to investigate, not wins to advertise.

### Problem

FlyRank's internship dataset contained 86,574 eligible pages across 22 pseudonymized clients.
Review attention was limited. I needed to test whether five signals available by March 20 could
rank which pages deserved diagnosis first, without using the March 21–31 outcome window as input.

### What I did and decided

I built the work as a reproducible ranking pipeline, not a production system. A transparent rule
and constant dummy set the reference points. A constrained random forest used 200 trees, maximum
depth 10, minimum leaf size 20, 80% feature sampling, and seed 42. I split by client: 16 clients
for training and six unseen clients for a 10,253-page holdout, with zero client overlap.

The decisive choice was what not to accept. I deliberately added a future field as a negative
control. It produced an invalid 1.000 NDCG, demonstrating how leakage could look like a perfect
model, and I excluded it. Public artifacts use only aggregate evidence and omit client identities,
URLs, titles, and raw queries.

### Outcome

| Holdout metric | Rule baseline | Random forest | What it means |
|---|---:|---:|---|
| Median client NDCG@20 | 0.690 | 0.797 | Better graded ordering near the top on this split |
| Mean precision@20 | 0.917 | 0.850 | A lower top-20 hit rate and more review effort |
| MAE | 0.486 | 0.430 | Lower average error on the opportunity proxy |

The valid model improved median client NDCG@20 by 15.5% relative to the rule and reduced MAE by
11.5%, but it did not win on every metric. Its bootstrap 95% interval for median client NDCG@20
was 0.405–0.876 across six holdout clients. That wide interval, the weaker precision, and the
proxy target rule out claims of broad robustness, production readiness, causal traffic lift, or
revenue impact. The defensible output is a 60-row, human-reviewed prioritization queue—never an
automatic instruction to publish, rewrite, delete, redirect, or de-index a page.

**Evidence:** [`work/capstone_report.md`](../../work/capstone_report.md) and the reproducible
notebooks and committed metric receipts it references.

## Case 2 — A boundary for every AI-assisted task

> An AI explanation is only a hypothesis until reruns verify it.

### Problem

I needed a repeatable way to use AI without silently outsourcing the judgments that determine
whether internship work is correct, defensible, or personally mine.

### What I did and decided

I audited 15 recurring internship tasks and assigned each one of four roles: Collaborate with AI,
Delegate to AI with review, Fully automate, or Just me. The boundary depends on the judgment and
verification a task requires. Deterministic test, formatting, schema, file, metric, and secret
checks can be automated. Drafting and checklist mechanics can be delegated only with review.
Framing and explanation stay collaborative. Interpreting metrics, approving public claims, and
making career choices stay with me.

I then made three common tasks falsifiable instead of vague:

1. An assignment checklist must cover every deliverable and pass/revise criterion, with zero
   uncovered acceptance criteria.
2. A notebook fix must preserve the error, separate cause from symptom, apply the smallest safe
   change, and pass two top-to-bottom runs with a fixed seed and materially identical metrics.
3. A public ML summary must be 150–200 words, include a baseline, two verified metrics, and a real
   limitation, and trace every number to a saved output or committed receipt.

### Outcome

The result is a checkable operating protocol for planning, diagnosis, verification, and public
claims. It identifies where AI can act and where human accountability cannot be delegated. It is
also deliberately limited: this self-authored audit does not prove consistent compliance,
productivity gains, optimal categories, or independent validation. Its value is that later work
can test the written boundaries instead of relying on an unrecorded intention.

**Evidence:** [`ai-fluency/FL-01/workflow-audit.md`](../FL-01/workflow-audit.md).

## Short bio

I'm Hisham Sabry, a machine-learning intern focused on rigorous evaluation of ranking models. I
prefer reproducible code, transparent baselines, and limitations shown beside headline metrics.

## Contact / call to action

If you're evaluating candidates for a junior machine-learning engineering opportunity and this
level of evaluation discipline matters, email me. I can walk through the split, baseline, model,
tradeoffs, rejected leakage test, and exact verification path.

## Generic line: before and after

**Before — generic AI copy**

> I am a results-driven machine learning professional passionate about leveraging cutting-edge AI
> to deliver impactful solutions.

**After — edited into my voice**

> I evaluate ranking models with grouped holdouts, transparent baselines, and the weaker metrics
> shown beside the wins.

The edit removes “results-driven,” “passionate,” “cutting-edge,” and “impactful”—claims that say
nothing specific and are not supported by receipts. The replacement names the work, the method,
and the standard I can defend.
