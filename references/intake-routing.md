# Intake and Routing

Run this **before** triage or drafting. Wrong artifact family wastes the entire rebuttal.

## Prerequisite: venue research

Complete [intake-venue-research.md](intake-venue-research.md) first unless the user explicitly waives it.

- Output: `VENUE_BRIEF.md` in the project rebuttal folder (template: [templates/venue-brief-template.md](templates/venue-brief-template.md)).
- Use brief limits over stale matrix rows when they conflict.
- Record Official Comment / AC-only / Author's Advocate availability in the brief.

## Required inputs

| Input | Required? | Notes |
|-------|-----------|-------|
| Venue name + year | Yes | e.g. CVPR 2026, ACM MM 2026, Nature Communications |
| Raw reviews (all reviewers) | Yes | Paste, PDF, or export |
| Scores + confidence | Strongly recommended | Drives champion strategy |
| Paper PDF or LaTeX | Yes for substantive draft | For evidence grounding |
| Editor decision letter | Journal only | Process before reviewer IDs |
| Character/word/page limit | Yes if stated | From `VENUE_BRIEF.md` (live lookup), not memory |
| `VENUE_BRIEF.md` | Yes (default) | Step 0 venue research artifact |
| Rebuttal round | If applicable | initial / follow-up / final remarks |

If venue or limit is unknown, **stop and ask** or assume the most conservative policy for that venue family.

## Artifact family router

| Family | Code | Typical venues | Output |
|--------|------|----------------|--------|
| One-page PDF | `ONE_PAGE_PDF` | CVPR, ICCV, ECCV; any venue whose current form requests a one-page PDF | `rebuttal.tex` → 1-page PDF |
| Per-review text | `PER_REVIEW_TEXT` | ICML, KDD, WWW Industry | One text block per reviewer + char limit |
| Threaded discussion | `THREADED_DISCUSSION` | NeurIPS, ICLR, ICLR-style, UAI, **ACM MM** | OpenReview thread(s), optional revised PDF |
| Journal point-by-point | `JOURNAL_POINT_BY_POINT` | Nature family, major/minor revision journals | Response letter + change map |
| Rolling revision | `ROLLING_REVISION` | ARR, TMLR | Short response + next-version revision plan |

Load the matching artifact guide from `references/artifacts/`.

## Quick venue map (common)

| Venue | Family | Hard limit | Revised PDF in rebuttal? | External links? |
|-------|--------|------------|--------------------------|-----------------|
| CVPR / ICCV / ECCV | `ONE_PAGE_PDF` | 1 page incl. figs/refs | No (rebuttal only) | **No** |
| ICML | `PER_REVIEW_TEXT` | 5000 chars / review | 2026: no upload during response | Anonymized URLs restricted |
| NeurIPS / ICLR | `THREADED_DISCUSSION` | Venue-managed | Often yes (ICLR) | Policy varies |
| ACM MM | usually `THREADED_DISCUSSION`; override to `ONE_PAGE_PDF` if OpenReview requires PDF | Check OpenReview form | Check CFP | Check CFP |
| KDD Research | `PER_REVIEW_TEXT` | Per-review window | Check CFP | Check CFP |
| ARR | `ROLLING_REVISION` | Text response | Revision later | No images/links in response |
| TMLR | `ROLLING_REVISION` | Public discussion | Multiple revision cycles | Public |
| Nature / Springer | `JOURNAL_POINT_BY_POINT` | Editor letter | Full revision package | Citations OK |

Full table: [venue-matrix.md](venue-matrix.md).

## Task mode (orthogonal to family)

| Mode | When | Output |
|------|------|--------|
| `triage-only` | User wants strategy before writing | Issue Board + strategy summary only |
| `plan` | No Issue Board yet | Board + experiment plan |
| `draft` | Ready to write | Full rebuttal draft |
| `audit` | Existing draft | Gap report + fixes |
| `revise` | User draft needs editing | Revised draft |
| `followup` | New reviewer messages | Delta reply only |

## Dual output convention

Unless the user asks otherwise:

1. **Paste-ready** — fits venue limit (PDF compile or plain text for OpenReview).
2. **Extended (internal)** — full evidence, `[INTERNAL]` notes, optional paragraphs marked `[CUT IF OVER LIMIT]`.

CV `ONE_PAGE_PDF` usually ships paste-ready = compiled PDF; extended = rich markdown for team review.

## Compression layer trigger

After Draft, always load [compression/space-engineering-router.md](compression/space-engineering-router.md):

- `ONE_PAGE_PDF` → `one-page-pdf-latex.md` + `visual-density-patterns.md`
- `PER_REVIEW_TEXT` or `THREADED_DISCUSSION` → `text-budget-markdown.md` + `visual-density-patterns.md` (tables in text)

## ACM MM default

Project path `ACMMM/rebuttal/` → default **`THREADED_DISCUSSION`**, but **the live OpenReview form wins**. If the form or user-provided screenshot specifies a **one-page PDF**, route to `ONE_PAGE_PDF` and record this override in `VENUE_BRIEF.md`. If OpenReview specifies a character cap per post, also apply `per-review-text.md` budget rules to each thread.
