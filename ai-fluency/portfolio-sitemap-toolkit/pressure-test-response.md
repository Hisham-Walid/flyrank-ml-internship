# Pressure-test response and decision

The response was generated in the configured Claude Project on 12 September 2026. This file
records the reviewed substance of the answer; it is not presented as independent evidence.

## Claude's verdict

Claude's strongest warning was that the proposed Work section risked presenting one body of
evidence as several projects. The FlyRank capstone and the “reproducible ML pipeline” use the
same dataset and receipts, so treating them as separate case studies would look like padding
and weaken the portfolio's honesty claim.

| Proposed item | Verdict | Reason |
|---|---|---|
| Home | Keep | It can route a busy hiring manager to the evidence quickly. The result preview must not hide the precision tradeoff. |
| FlyRank case study | Keep and make it the anchor | It directly proves the data, reproducibility, honest-evaluation, and human-review parts of the proof statement. |
| Reproducible ML pipeline | Merge into FlyRank | It is the method spine of the same project, not independent evidence. |
| Responsible AI workflow | Keep only as a shorter second case | It earns a separate place only because the workflow audit, review boundaries, and verification protocol are concrete artifacts distinct from the capstone. |
| About | Keep, but trim hard | It supplies credibility context but no project evidence. |
| Contact | Keep | It directly supports the one requested action. |

## Main risks identified

1. **Evidence inflation:** turning one dataset into multiple “projects” would be easy for a
   technical reviewer to detect.
2. **Cherry-picked preview:** showing only NDCG@20 improvement on the homepage while hiding the
   lower precision@20 would contradict the claim of honest evaluation.

## Exact change adopted

The Work section now launches with:

1. **FlyRank: Search-Opportunity Ranking** — one deep case containing the end-to-end pipeline,
   grouped holdout, NDCG and precision together, bootstrap uncertainty, limitations, action
   playbook, and human-review protocol.
2. **AI Fluency: Responsible Review Artifacts** — one shorter case backed by the distinct FL-01
   workflow audit, human-only boundaries, reusable verification checklist, and project
   instructions.

The homepage preview will lead with the six-client grouped holdout and human-review boundary,
then link to the case study for the full metric tradeoff. This is clearer than advertising only
the strongest number.

## Verification

- Project: **Hisham — ML Portfolio Build**
- Conversation: **Portfolio sitemap pressure test for ML/AI role**
- Generated: 12 September 2026
- No unverified evidence was accepted into the revised sitemap.
