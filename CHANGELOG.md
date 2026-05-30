# Changelog

## [1.3.0] — 2026-05-30

### Added

- **Experiment rebuttal router:** [references/experiment-rebuttal-router.md](references/experiment-rebuttal-router.md) — venue policy matrix, Tier A–D, feasibility labels, decision tree, push-back phrasing, distilled from CVPR/ICLR/NeurIPS policies + SKMP skills (EvoScientist, review-rebuttal, review2rebuttal) + FastJSMA case.
- **Experiment plan template:** [references/templates/experiment-plan-template.md](references/templates/experiment-plan-template.md).

### Enhanced

- Workflow expanded to **nine steps** with mandatory `EXPERIMENT_PLAN.md` when reviewers request new numbers.
- Issue Board schema: `experiment-class`, `experiment-tier`, `feasibility` fields.
- QA checklist: experiment plan gates.

## [1.2.0] — 2026-05-30

### Added

- **Citation verification (LightRead CLI):** [references/citation-verification-lightread.md](references/citation-verification-lightread.md) — `lr search`, `lr web fetch`, `lr websearch` workflow for fixing reviewer-flagged references before rebuttal submit.
- **Reviewer coverage audit:** [references/reviewer-coverage-audit.md](references/reviewer-coverage-audit.md) — pre-submit reviewer × concern × response map; score-lift heuristics; optional 中文 author sign-off table.
- **Diplomatic benchmark phrasing:** [references/phrasing/diplomatic-benchmark-rebuttal.md](references/phrasing/diplomatic-benchmark-rebuttal.md) — tactful language for scale comparison, eval-subset cost, QC/rubric space rebalancing (from ACM MM MemeSleuth-Bench rebuttal).

### Enhanced (from live rebuttal iteration)

- **Page-fill invariant** — one-page PDF must reach final lines unless venue/user exempts ([one-page-pdf-cv.md](references/artifacts/one-page-pdf-cv.md), [one-page-pdf-latex.md](references/compression/one-page-pdf-latex.md)).
- **Reviewer label mapping** — visible `R1=OpenReviewID` map when using shorthand ([one-page-pdf-cv.md](references/artifacts/one-page-pdf-cv.md)).
- **ACM-style PDF override** — non-official `acmart` template path when OpenReview requests PDF ([one-page-pdf-latex.md](references/compression/one-page-pdf-latex.md), [external-sources.md](references/external-sources.md)).
- **No-new-experiments mode** — evidence inventory, no invented IAA/human ceiling ([one-page-pdf-cv.md](references/artifacts/one-page-pdf-cv.md)).
- **QA checklist** — page-fill, reviewer map, citation verification, coverage audit gates.

## [1.1.0] — 2026-05-29

- Mandatory **Venue Research** (Step 0) → `VENUE_BRIEF.md`
- **Official Comment / AC-only note** artifact
- Public GitHub release

## [1.0.0] — Initial

- Router + shared kernel + five artifact families
