# External Rebuttal Sources (Distilled)

Structured summaries of public rebuttal guides. Use for provenance; canonical execution rules live in
core references and compression modules.

| Source | URL | Key patterns | Omnirebuttal home |
|--------|-----|--------------|-------------------|
| Devi Parikh, Dhruv Batra, Stefan Lee | https://deviparikh.substack.com/p/how-we-write-rebuttals-dc84742fece1 | AC-first; spreadsheet triage; quote-then-answer; respond to intent; @All merge; stats > words; don't promise—do; color-code reviewers | `strategy-decision.md`, `templates/` |
| Andreas Zeller | https://andreas-zeller.info/2012/10/01/patterns-for-writing-good-rebuttals.html | Identify the Champion; arm champion vs detractors; skip typos; focus persuadable reviewers | `strategy-decision.md` |
| Cesar Sotovalero | https://www.cesarsotovalero.net/blog/how-to-write-a-good-paper-rebuttal.html | Champion required; major concerns first; Markdown table rows count as one word (OpenReview); @All four-point summary | `compression/text-budget-markdown.md` |
| Yao et al. (CACM) | https://cacm.acm.org/opinion/rebuttal-how-to-strategies-tactics-and-the-big-picture-in-research/ | Paraphrase and reorder comments; limited space → new numbers; show revision commitment | `strategy-decision.md` |
| Tobias Grosser | https://grosser.science/howtos/paper-rebuttals/ | 3–5 principal arguments with argument-first titles; shorten backwards; drop minor formatting nits | `artifacts/one-page-pdf-cv.md` |
| Merrie Stanford | https://cs.stanford.edu/~merrie/merrie_rebuttal_tips.pdf | Be specific in promises: give numbers, paragraph text, or distinction vs prior work—not vague "we will add" | `safety-gates.md`, `templates/` |
| Niklas Elmqvist | https://niklaselmqvist.medium.com/writing-rebuttals-7f6949eddf6e | Mirror reviewer structure/numbering; 5000-char budget; facts over confrontation | `artifacts/per-review-text.md` |
| CVPR Author Kit | https://github.com/cvpr-org/author-kit/blob/main/rebuttal.tex | 1 page hard limit incl. figs/refs; two-column; no external links; fig width ~0.8 linewidth; separate fig/table numbering from main paper | `compression/one-page-pdf-latex.md` |
| Bill Freeman (CVPR18 panel, via Devi) | — | Rebuttal is for judges (AC), not opponents; crowded marketplace metaphor | `strategy-decision.md` |

## Devi Parikh — 18 tips (condensed)

1. Start positive — summarize strengths so AC does not forget them.
2. Order matters — biggest concerns with best answers first.
3. Quote reviewer, then answer directly in first sentence.
4. Be conversational, not combative.
5. Respond to intent, not only literal question.
6. Use emphasis where helpful ("Row 2 in Table 4 shows exactly that").
7. Set the stage if all reviewers missed a central point.
8. Keep self-contained — reintroduce acronyms and setup.
9. Get credit for details already in paper (cite line/table, then restate).
10. Consolidate common concerns (@All) to save space.
11. Color-code reviewers for navigation.
12. Stats speak louder than words.
13. Don't promise—do (show discussion/equation now, then say paper will update).
14. Be receptive and reasonable.
15. Be transparent about venue limits (no new experiments allowed, etc.).
16. Flag bad-faith reviewing factually (confidential AC note when allowed).
17. Acknowledge reviewer effort (typos, citations, future work suggestions).
18. Remember humans on the other end — find common ground.

## Cesar Sotovalero — space hacks (OpenReview text only)

- Markdown tables: one row ≈ one word in some systems → pack new experiments as tables.
- Underscore/dash concatenation for question headers: use sparingly; abuse may get rebuttal deleted.
- End with consolidated four-point summary addressing all reviewers.
- **Not applicable** to CV one-page PDF (no links, no markdown word-count hacks).

## Zeller — champion workflow

1. Identify potential champion (likes core idea, borderline score, says they may be swayed).
2. If no champion, acceptance odds are low — still rebut if champion exists.
3. Refute each detractor issue with facts the champion can reuse in discussion.
4. Do not waste space proving you can fix typos.

## Grosser — principal arguments

- Extract 3–5 arguments that matter for acceptance; title each with the **conclusion**, not the problem.
- Tag which reviewers each argument answers.
- When over length: shorten individual Q&A bullets, never shorten principal arguments.
- Drop category (c) minor formatting unless one opening sentence covers all.

## Live venue research (Omnirebuttal v1.1+)

Static rows in `venue-matrix.md` are **fallback only**. Each session must run [intake-venue-research.md](intake-venue-research.md):

- Official: venue author page, OpenReview stage docs, CFP track rules
- Community: 小红书 / 知乎 / Reddit / blogs — label `P2`, never override official policy
- Output: `VENUE_BRIEF.md` per project

## Official Comment sources

| Source | URL | Pattern |
|--------|-----|---------|
| OpenReview comment stage | https://docs.openreview.net/reference/stages/comment-stage | Official Comment invitations; reader dropdown |
| OpenReview rebuttal stage | https://docs.openreview.net/reference/stages/rebuttal-stage | Author Rebuttal vs comment forms |
| OpenReview hide/reveal readers | https://docs.openreview.net/how-to-guides/submissions-comments-reviews-and-decisions/how-to-hide-reveal-fields | AC-only restricted fields |
| inno-rebuttal platforms | skmp `platforms_and_policies.md` | Confidential AC note checklist |
| Devi tip #16 | substack | Bad-faith → confidential AC note when allowed |

Canonical workflow: [artifacts/official-comment.md](artifacts/official-comment.md).
