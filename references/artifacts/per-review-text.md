# Artifact: Per-Review Text (ICML, KDD, …)

**Family:** `PER_REVIEW_TEXT`  
**Output:** One text block per reviewer; paste into OpenReview/CMT field.

## Structure (per reviewer)

```text
[Brief thanks if not in global opener — optional]

**W1 / Q1 — [paraphrased concern]**
[Direct answer sentence.] [Evidence: table or numbers.] [Paper revision note if any.]

**W2 — ...**
...
```

Mirror reviewer numbering when provided (Niklas Elmqvist).

## Character budget (ICML 5000 example)

| Section | Share |
|---------|-------|
| Opener (once, or first review only) | 10–15% |
| This reviewer's body | proportional to pivotal weight |
| Closing (once global) | 5–10% |

Pivotal reviewers (`reviewer_priority: pivotal`) get longer bodies.

Verify each file:

```bash
scripts/count_limits.sh Reviewer_R1_response.txt --chars --limit 5000
```

## Global vs per-review content

| Content | Where |
|---------|-------|
| Shared baseline table | Global comment OR first pivotal review + pointers in others |
| Strengths summary | Once in opener or first response |
| Minor typos batch | One global sentence |

ICML encourages addressing **major misunderstandings** over every minor point.

## Dual output

1. **Paste-ready** — under char limit, plain text/markdown as venue accepts
2. **Extended** — full tables, `[CUT IF OVER LIMIT]` sections

## Multi-round (ICML 2026: 3 rounds)

- Round 1: full per-review responses
- Round 2+: **delta only** — new questions; back-reference: "As noted in our initial response, …"
- Stop arguing after ~3 rounds on same point

## Compression

[../compression/text-budget-markdown.md](../compression/text-budget-markdown.md)

## Self-contained rule

Each reviewer's block must make sense without reading other reviewers' posts (unlike threaded mode with strict isolation, but avoid "see R2").

## QA additions

- [ ] Each reviewer file under limit
- [ ] Pivotal reviewers adequately covered
- [ ] No empty "we will add experiments"
