---
name: omnirebuttal
description: >-
  Unified author-response skill for all peer-review rebuttal formats: CV one-page PDF
  (CVPR/ICCV/ECCV), OpenReview threaded discussion (NeurIPS/ICLR/ACM MM), per-review
  character limits (ICML/KDD), Nature/journal point-by-point revision letters, and
  ARR/TMLR rolling revision. Routes by venue artifact family after shared triage, strategy,
  compression, safety gates, and mandatory per-venue web research (official + community).
  Supports Official Comment / AC-only notes when appropriate. Triggers: rebuttal, author response, 审稿回复, 逐点回复,
  修回信, OpenReview response, response to reviewers, one-page rebuttal, rebuttal strategy.
version: 1.1.0
---

# Omnirebuttal

Turn reviewer feedback into a venue-correct, evidence-backed author response. **Router + shared
kernel + specialized artifact branches** — not a lowest-common-denominator merge.

## When to use

- Conference rebuttal (CV one-page PDF, OpenReview, ICML per-review text)
- Journal major/minor revision response letters (Nature-style point-by-point)
- ARR/TMLR rolling review responses
- Rebuttal strategy, Issue Board, or REVISION_PLAN without full draft (`triage-only`)

## Seven-step workflow

0. **Venue Research (mandatory)** — Read [references/intake-venue-research.md](references/intake-venue-research.md): search **official** rules + **community** tips (官网, OpenReview, 小红书, 知乎, Reddit, …) via **web-access**; write `VENUE_BRIEF.md` before drafting.
1. **Intake & Route** — Read [references/intake-routing.md](references/intake-routing.md): venue, artifact family, limits, task mode (informed by brief).
2. **Triage** — Read [references/triage-issue-board.md](references/triage-issue-board.md): Issue Board + merge map.
3. **Strategy** — Read [references/strategy-decision.md](references/strategy-decision.md): champion, color-code, postures; flag AC escalation / Official Comment need.
4. **Draft** — Load **one** primary artifact from [references/artifacts/](references/artifacts/); add [official-comment.md](references/artifacts/official-comment.md) when strategy warrants.
5. **Compress & Fit** — Read [references/compression/space-engineering-router.md](references/compression/space-engineering-router.md); apply PDF or text compression; run `scripts/count_limits.sh` when applicable.
6. **Safety + QA** — [references/safety-gates.md](references/safety-gates.md) + [references/qa-checklist.md](references/qa-checklist.md).

## Artifact family router

| Family | Venues (examples) | Artifact file | Output |
|--------|-------------------|---------------|--------|
| `ONE_PAGE_PDF` | CVPR, ICCV, ECCV | [one-page-pdf-cv.md](references/artifacts/one-page-pdf-cv.md) | 1-page `rebuttal.tex` / PDF |
| `PER_REVIEW_TEXT` | ICML, KDD | [per-review-text.md](references/artifacts/per-review-text.md) | Text per reviewer + char limit |
| `THREADED_DISCUSSION` | NeurIPS, ICLR, UAI, **ACM MM** | [threaded-openreview.md](references/artifacts/threaded-openreview.md) | OpenReview thread(s) |
| `JOURNAL_POINT_BY_POINT` | Nature, R&R journals | [journal-point-by-point.md](references/artifacts/journal-point-by-point.md) | Response letter + change map |
| `ROLLING_REVISION` | ARR, TMLR | [rolling-arr-tmlr.md](references/artifacts/rolling-arr-tmlr.md) | Response + revision plan |
| *(secondary)* Official Comment / AC note | When strategy flags escalation | [official-comment.md](references/artifacts/official-comment.md) | Restricted or public chair-facing note |

Venue details: [references/venue-matrix.md](references/venue-matrix.md).

## Progressive loading

| Need | Read |
|------|------|
| **Live venue rules + community tips** | intake-venue-research.md → `VENUE_BRIEF.md` |
| Venue / family / mode | intake-routing.md, venue-matrix.md |
| Official Comment / AC-only note | artifacts/official-comment.md |
| Issue Board | triage-issue-board.md |
| Champion, ordering, postures | strategy-decision.md |
| Provenance / promises / coverage | safety-gates.md |
| One-page PDF layout, tiny tables, figs | compression/one-page-pdf-latex.md |
| OpenReview char budget, markdown tables | compression/text-budget-markdown.md |
| Table vs figure choice | compression/visual-density-patterns.md |
| Copy-ready phrases | templates/response-templates.md |
| ICCV 2025 win case | cases/fastjsma-iccv2025.md |
| Source provenance (web + SKMP) | external-sources.md |

## Default stance (all families)

- **AC / editor first** — rebuttal may be all they read.
- **Don't promise—do** — show table, equation, or paragraph now; then note paper update.
- Every Issue Board item gets an anchor; merge duplicates via `@All` or `merge_key`.
- No invented numbers, citations, or manuscript edits (three safety gates).

## Standard output package

Unless the user asks otherwise:

```text
VENUE_BRIEF.md (official limits + community intel + sources)
Response strategy summary
Comment tracker (Issue Board + merge map)
Draft rebuttal / response letter (venue-specific)
Official Comment / AC-only note (if warranted)
Manuscript follow-ups (REVISION_PLAN)
Risk flags / AUTHOR_INPUT_NEEDED
中文核对 (optional)
```

## Tools

```bash
# Character limit check (OpenReview / ICML text)
scripts/count_limits.sh draft.txt --chars --limit 5000
```

## Legacy skill

CV-only workflows previously used `conference-rebuttal-playbook` — now superseded by
`artifacts/one-page-pdf-cv.md` within this skill. Playbook remains as deprecated redirect.

## What this skill does NOT do

- Run experiments automatically
- Submit to OpenReview / CMT
- Replace venue-specific legal/policy advice — verify CFP before final submit
