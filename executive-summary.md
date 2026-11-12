# Executive Summary: Model Sourcing Brief — BERT Family Evaluation

**Prepared for:** Platform Review (due Friday)
**Hub account tied to team access:** @lhz7891444 (https://huggingface.co/lhz7891444) — user account, personal access token with write role, no visible organization memberships.

## Incumbent Model

- **Model:** google-bert/bert-base-uncased (https://hf.co/google-bert/bert-base-uncased)
- **Downloads (current, per Hub):** ~3,292.5M (3.29B)
- **Likes (current, per Hub):** 3,068
- **Details:** 110.1M-parameter fill-mask model (bert architecture), apache-2.0 license, last updated 19 Feb 2024. Has been the sole model running through our search stack since launch.

## Candidate Shortlist (top 3 most-downloaded BERT-family models on the Hub, excluding the incumbent)

| # | Model Identifier | Downloads | Likes |
|---|------------------|-----------|-------|
| 1 | google-bert/bert-base-cased | 3.3M | 398 |
| 2 | google-bert/bert-base-multilingual-uncased | 2.0M | 177 |
| 3 | google-bert/bert-base-multilingual-cased | 1.5M | 623 |

## Deliverables Location

- **Word brief:** model_sourcing_brief.docx (saved in the shared workspace at /tmp/mcp_ws/model_sourcing_brief.docx)
- **Snowflake warehouse table:** SEARCH_EVAL.MODEL_EVALS.MODEL_SOURCING
  - One row per shortlisted model plus one row for the incumbent (model identifier, download count, like count)
  - Verification query `SELECT COUNT(*) AS ROW_COUNT FROM SEARCH_EVAL.MODEL_EVALS.MODEL_SOURCING;` returned **ROW_COUNT = 8** (our 4 loaded rows plus 4 pre-existing rows in the table)

## Recommended Next Steps

1. Schedule a platform review to evaluate whether any of the three candidates should replace google-bert/bert-base-uncased as the default for the search stack.
2. Validate the shortlisted models against current query patterns and quality benchmarks before any production commitment (bert-base-cased leads on downloads at 3.3M among non-incumbent BERT-family models).
3. Maintain the incumbent and shortlist rows in SEARCH_EVAL.MODEL_EVALS.MODEL_SOURCING for auditability against live Hub download and like counts.
