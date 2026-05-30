# Space Engineering Router

Load **after Draft**, before Safety gates. Compression is not a separate artifact family—it optimizes fit for the chosen family.

## Router

| Artifact family | Primary compression doc | Secondary |
|-----------------|---------------------------|-----------|
| `ONE_PAGE_PDF` | [one-page-pdf-latex.md](one-page-pdf-latex.md) | [visual-density-patterns.md](visual-density-patterns.md) |
| `PER_REVIEW_TEXT` | [text-budget-markdown.md](text-budget-markdown.md) | visual-density-patterns.md |
| `THREADED_DISCUSSION` | text-budget-markdown.md | visual-density-patterns.md |
| `JOURNAL_POINT_BY_POINT` | text-budget-markdown.md (prose density) | visual-density-patterns.md (optional figures in letter) |
| `ROLLING_REVISION` | text-budget-markdown.md | — |

## Fit-check loop

1. Measure: compile PDF page count OR `scripts/count_limits.sh <file> --chars --limit N`
2. If over limit → apply family-specific trim order (see child docs)
3. **Text-condense pass** on prose blocks: preserve numbers, citations, claims; remove filler (RebuttalStudio text-condense rules)
4. Re-measure; repeat max 2 internal rounds
5. If still over: flag `AUTHOR_INPUT_NEEDED` — do not drop red-tier evidence silently

## What NOT to compress first

- Must-win experimental tables/figures
- Reproducibility pipeline explanations (critical severity)
- Direct answers to pivotal reviewer questions

## Trim priority (universal)

1. Duplicate context across reviewer blocks → merge to @All
2. Repeated method descriptions → one setup paragraph + pointers
3. Minor/gray issues → one batched sentence
4. Opener/closing fluff → one line each
5. Word-level condense on orange/gray prose only

## Dual version

Keep **extended** draft with `[CUT IF OVER LIMIT]` markers; produce **paste-ready** by stripping marked blocks last.
