# QA Checklist

Run after Compress & Fit, before submit.

## Venue research (Step 0)

- [ ] `VENUE_BRIEF.md` exists with P0 official fields filled (or user waived with log)
- [ ] Artifact family matches brief, not guess
- [ ] Hard limits verified against OpenReview form / author page
- [ ] Community tips labeled P2 and cross-checked against official policy
- [ ] Official Comment / AC channel rules recorded if applicable

## Universal (all families)

### Coverage
- [ ] Every Issue Board ID mapped to response anchor
- [ ] All `merge_key` clusters have single home (@All or designated block)
- [ ] Editor instructions (`E.*`) answered before reviewers (journal)
- [ ] Follow-up round: only new deltas; back-reference prior answers

### Provenance
- [ ] No invented numbers, citations, or experiments
- [ ] New results tagged `user_confirmed_result`
- [ ] Paper citations (Table X, §Y) verified against manuscript

### Commitment
- [ ] Every "we will revise" has REVISION_PLAN item or `future_work_only` label
- [ ] Merrie test: specific text/numbers shown where feasible
- [ ] No impossible promises before deadline

### Tone
- [ ] Direct answer in first sentence after each quoted concern
- [ ] Conversational, not combative
- [ ] Genuine thanks for constructive points (typos, citations)

### Structure
- [ ] Opening cites 2–3 strengths with reviewer tags
- [ ] Biggest concerns answered first (not reviewer order)
- [ ] Self-contained: acronyms and setup reintroduced

### Consistency
- [ ] No contradictory answers across reviewers
- [ ] Numbers match submission unless new result explicitly labeled

## ONE_PAGE_PDF additions

- [ ] Compiles to **≤1 page** (figures + refs included)
- [ ] Official template; margins/fonts unchanged
- [ ] **No external links**
- [ ] Figures legible when **printed** (not zoom-only)
- [ ] Fig/table numbering disjoint from main paper if needed
- [ ] @All shared table/figure present for merged major concerns

## PER_REVIEW_TEXT additions

- [ ] Each reviewer response within char limit (`scripts/count_limits.sh --chars --limit N`)
- [ ] Budget: opener 10–15%, body 75–80%, closing 5–10%
- [ ] Pivotal reviewers get disproportionate space

## THREADED_DISCUSSION additions

- [ ] Each thread self-contained (no "see R2's response")
- [ ] Follow-up ≤3 rounds unless new substantive issue
- [ ] Revised PDF claims match rebuttal if upload allowed
- [ ] Official Comment drafted only when strategy flagged; not a duplicate rebuttal

## Official Comment / AC-only (when drafted)

- [ ] Science remains in main rebuttal; AC note is meta / factual dispute only
- [ ] Readers / channel match `VENUE_BRIEF.md`
- [ ] No ad hominem; quotes accurate
- [ ] `user_confirmed_official_comment` before paste to OpenReview

## JOURNAL_POINT_BY_POINT additions

- [ ] Reviewer comment preserved faithfully before response
- [ ] Each response maps to change location or justified disagreement
- [ ] Package readiness: `ready_to_submit` | `draft_with_placeholders` | `needs_author_input`
- [ ] Optional LaTeX: referee wrote / our reply / changes structure complete

## ROLLING_REVISION additions

- [ ] Revision plan for next version explicit
- [ ] ARR: no disallowed links/images
- [ ] Long argumentative exchanges trimmed

## Compression pass

- [ ] Overflow resolved via compression module (not by dropping red-tier evidence)
- [ ] Tables used for dense numeric evidence where appropriate
- [ ] No AI filler phrases ("It is worth noting that…" as opener)

## RebuttalStudio self-review (optional deep pass)

From `rebuttal-self-review`: coverage scan, tone pass, factual spot-check (3–5 claims), structure skim.

## Output package complete?

- [ ] VENUE_BRIEF.md
- [ ] Response strategy summary
- [ ] Comment tracker (Issue Board)
- [ ] Draft rebuttal (venue-specific)
- [ ] Official Comment / AC note (if strategy required)
- [ ] REVISION_PLAN / manuscript follow-ups
- [ ] Risk flags / AUTHOR_INPUT_NEEDED
- [ ] 中文核对 (if user writes in Chinese)
