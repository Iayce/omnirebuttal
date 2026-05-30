# Venue Matrix (Condensed)

Use with [intake-routing.md](intake-routing.md). **Prefer live `VENUE_BRIEF.md`** from [intake-venue-research.md](intake-venue-research.md) over this table for limits and channels.

## By family

### ONE_PAGE_PDF (CVPR, ICCV, ECCV)

- Optional 1-page PDF rebuttal via official template.
- No iterative author-reviewer exchange in rebuttal phase.
- Anonymity required; **no external links**.
- Optional **confidential comment to AC** (verify year) — not a second rebuttal page.
- Reviewers discouraged from penalizing lack of huge new experiments; authors should not add unrequested major new results.
- Workflow: merge repeated concerns → 2–4 decision-critical issues → compact table/figure if allowed.

### PER_REVIEW_TEXT (ICML, KDD, …)

- One official response per review (e.g. ICML 5000 characters).
- Acknowledgment + optional further rounds (ICML 2026: 3 rounds).
- Budget: opener 10–15%, body 75–80%, closing 5–10%.
- Prioritize major misunderstandings over every minor point (ICML guidance).
- **Confidential AC comments** exist but must **not** substitute for per-review responses.

### THREADED_DISCUSSION (NeurIPS, ICLR, UAI, ACM MM)

- OpenReview-style discussion; may allow revised PDF (ICLR).
- Per-reviewer threads may need self-contained replies (no "see R2").
- Follow-up: delta replies only; cap at ~3 rounds per thread when stuck.
- Track `pdfdiff` / large revision warnings when venue shows diffs to reviewers.
- **Official Comment** / AC-only channels: venue-specific — record in `VENUE_BRIEF.md`; see [artifacts/official-comment.md](artifacts/official-comment.md).
- **ACM MM**: one rebuttal per review; no external links; Author's Advocate for sub-standard reviews ([2025 authors](https://acmmm2025.org/information-for-authors/)).

### JOURNAL_POINT_BY_POINT (Nature, R&R journals)

- Editor instructions first (`E.1`, …), then reviewers (`R1.1`, …).
- Map every response to manuscript location or `AUTHOR_INPUT_NEEDED`.
- Response letter is editor-facing verification document.

### ROLLING_REVISION (ARR, TMLR)

- ARR: no images/external links; small responsive experiments OK; long arguments low value.
- TMLR: public discussion; emphasize revision plan for next manuscript version.
- Shift from debate to "what changes in the next submission."

## Interaction style vs artifact

| Style | Examples | Author focus |
|-------|----------|--------------|
| One-shot | CVPR, ECCV | Single dense PDF |
| Per-review + discussion | ICML, KDD | Char budget per reviewer |
| Threaded | ICLR, NeurIPS, UAI | Quick major concerns + follow-ups |
| Rolling | ARR, TMLR | Resolve core issues, plan revision |
| Single feedback | AAAI phase-2 | Short unified feedback response |

## Policy red lines (cross-venue)

- Do not invent experiments, numbers, citations, or manuscript edits.
- Do not break anonymity (CV / double-blind venues).
- Do not use CV-style external links in PDF rebuttals.
- Do not promise camera-ready changes you cannot deliver (Commitment gate).

Sources: distilled from inno-rebuttal `venue_rule_matrix.md`, CVPR/ICML author guides, ARR author FAQ.
