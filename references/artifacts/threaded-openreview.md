# Artifact: Threaded OpenReview (NeurIPS, ICLR, UAI, ACM MM)

**Family:** `THREADED_DISCUSSION`  
**Output:** OpenReview author comment(s); may include revised PDF upload (ICLR-style).

## VENUE_MODE

| Mode | When | Rule |
|------|------|------|
| `single_document` | One shared author response | Global opener + per-reviewer sections in one post |
| `per_reviewer_thread` | Each reviewer thread separate | **Self-contained** files; no "see Reviewer X" |

Default ACM MM: check OpenReview — often `single_document` or unified rebuttal field; use per-thread if UI requires.

## single_document structure

```text
1. Short opener (thanks + 2 strengths + 2–4 global resolutions)
2. @R1 numbered responses (answer → evidence → implication)
3. @R2 ...
4. @All shared table for merged concerns
5. Closing: resolved / remaining / accept case
```

Artifacts: `REBUTTAL_DRAFT_rich.md`, `PASTE_READY.txt` (plain text + char count).

## per_reviewer_thread structure

Each `Reviewer_<ID>_response.md`:

1. Brief acknowledgment of that reviewer's thrust
2. Numbered W#/Q# responses
3. Optional shared `SETUP_METRICS_BLOCK.md` pasted consistently (≤150 words)

**Forbidden:** cross-thread references undefined in that file.

## Follow-up rounds

1. Append new comments to `FOLLOWUP_LOG.md`
2. Update Issue Board (new issues or reopen)
3. Draft **delta reply only**
4. Re-run safety gates
5. Cap persistent disagreement at ~3 rounds — summarize positions for AC
6. Re-run **venue research delta** if new OpenReview round or policy change

## Official Comment vs Rebuttal

| Use | Channel |
|-----|---------|
| Answer reviewer science | **Author Rebuttal** (primary) |
| Factual review error already in rebuttal; AC must weigh | **AC-only Official Comment** (if enabled) |
| Sub-standard review | **Author's Advocate** (ACM MM) or AC-only note |

Full workflow: [official-comment.md](official-comment.md). Confirm channels in `VENUE_BRIEF.md` from Step 0.

## OpenReview intake (ml-research)

- Prefer pasted review text if fetch/login blocked
- Record scores, confidence, meta-review
- Parse atomic issues before drafting

## Revised PDF (when allowed)

- Large unexplained revisions may be ignored (ICLR pdfdiff warning)
- Match rebuttal promises to visible diff
- Do not contradict rebuttal in uploaded PDF

## Compression

[../compression/text-budget-markdown.md](../compression/text-budget-markdown.md) — tables, @All, Q/A format.

If character cap per post exists, treat as `PER_REVIEW_TEXT` budget per thread.

## REVISION_PLAN

Track promises separately:

```markdown
- [ ] (R1-C2) Clarify §3.1 assumption hierarchy — approved_for_rebuttal
```

## QA additions

- [ ] Thread-local self-containment (per_reviewer_thread mode)
- [ ] Follow-up deltas only (no full rewrite each round)
- [ ] Anonymity preserved in links and text

## ACM MM note

Project default: `THREADED_DISCUSSION`. Input reviews from `ACMMM/rebuttal/`; output OpenReview-ready markdown + Issue Board + REVISION_PLAN.

Before drafting: complete `ACMMM/rebuttal/VENUE_BRIEF.md` via [intake-venue-research.md](../intake-venue-research.md).

Known policy anchors (verify yearly in brief):

- One rebuttal per review; concise; **anonymous**; **no external links**
- Rebuttal optional; address factual errors / requested clarifications — not new contributions
- Reviewers instructed not to treat new rebuttal experiments as decision basis
- **Author's Advocate** for demonstrably sub-standard or false reviews ([ACM MM 2025 authors](https://acmmm2025.org/information-for-authors/))
