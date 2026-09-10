# Ranking content-review opportunities from pre-decision search signals

- **Author:** Hisham
- **Lane:** Applied Search Intelligence — page-level review prioritization
- **Repository:** <https://github.com/Hisham-Walid/flyrank-ml-internship>
- **Analysis date:** 2026-09-10

## 0. Abstract

This study asks whether pre-decision Google Search Console aggregates can help a content
strategist rank pages for manual review. It uses the March 2026 FlyRank ML Internship release,
aggregates March 1–20 into five features, and measures a March 21–31 missed-click opportunity
proxy on 86,574 eligible pages. A fixed-seed random forest is compared with a transparent rule
and a constant dummy on the same six-client grouped holdout, with no client overlap. The model
measured median client NDCG@20 of 0.797, a 15.5% relative gain over the rule baseline's 0.690,
while mean precision@20 decreased from 0.917 to 0.850 and the six-client bootstrap interval
remained wide. The output is therefore a human-reviewed prioritization queue, not an automatic
editing system or a claim of causal traffic lift.

## 1. Problem framing

At a March 20 decision point, can five observable search-performance aggregates rank page-level
future missed-click opportunity better than a transparent review rule for clients unseen during
training? The unit is an aggregated pseudonymous content page. A content strategist receives a
within-client rank and suggested action. False positives consume review time and may encourage
unnecessary edits; false negatives delay inspection of a potentially valuable page.

## 2. Data safety

The approved source is the March 2026 `fact_content_daily_performance` partition from the
FlyRank ML Internship warehouse. The feature window is March 1–20 and the observed outcome
window is March 21–31; June remained sealed. Five pre-decision GSC aggregates are features.
Client/content hashes are grouping context only. Future fields, identifiers, product trend
fields, URLs, titles, raw queries, and GA4 fields are excluded from model features and public
artifacts. Eligibility leaves 86,574 pages across 22 pseudonymized clients and excludes
disappearing and very low-volume pages.

## 3. Baseline

The rule scores pages with at least 500 prior impressions, prior average position 4–20, and CTR
below a position-band benchmark estimated only on training clients. On the six-client holdout it
measured median client NDCG@20 of 0.690, mean precision@20 of 0.917, and MAE of 0.486.

## 4. Model / analysis

The target is future impressions times the positive gap between observed future CTR and the
training clients' CTR for the same future-position band. The random forest uses 200 trees,
maximum depth 10, minimum leaf size 20, 80% feature sampling, and seed 42. Features are prior
impressions, clicks, average position, active days, and CTR. The proxy is opportunity magnitude,
not incremental clicks or revenue.

## 5. Evaluation

A fixed 75/25 client-grouped split places 16 clients in training and six entirely unseen clients
in test (10,253 pages; zero overlap). The random forest measured median client NDCG@20 0.797,
mean precision@20 0.850, and MAE 0.430. Relative to the rule, NDCG improved 15.5% and MAE fell
11.5%, but precision@20 was lower; the held-out positive-target base rate was 0.626. The
bootstrap 95% interval for median client NDCG@20 was
0.405–0.876. A deliberate future-field leak produced an invalid 1.000 NDCG and was rejected.

## 6. Interpretation

Prior impressions and prior CTR produced the largest permutation drops in grouped NDCG. This
means visibility scale and earlier click capture were the most useful ranking signals for this
fitted model and split. It does not mean either causes future opportunity. Prior clicks produced
a slightly negative permutation result, suggesting it added little beyond impressions and CTR.

## 7. Recommendation

The 60-row playbook selects ten candidates per held-out client and requires human review for
every row. Review page-one under-capture candidates for intent and snippet fit first; inspect
striking-distance candidates for verified freshness or coverage gaps; protect strong top-three
assets; and wait for more evidence on thin-history pages. Never auto-publish, rewrite, delete,
redirect, de-index, retrain, or claim uplift from this queue.

## 8. Reproducibility

Install `requirements.txt`; provide approved data through `HF_TOKEN` or
`FLYRANK_MARCH_PARQUET`; execute `w05_model.ipynb`, `w06_validation_audit.ipynb`,
`w07_action_playbook.ipynb`, and `capstone.ipynb` in order. Randomized steps use seed 42. The
committed JSON receipts preserve the exact metrics, and the capstone notebook regenerates all
aggregate paper figures.

## 9. Acknowledgments & data credit

Built on the [FlyRank ML Internship dataset](https://flyrank.ai). The analysis is an independent
internship project; FlyRank provided the anonymized training release and learning framework.
