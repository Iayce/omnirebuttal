# Text Budget (OpenReview / ICML / Markdown)

For `PER_REVIEW_TEXT` and `THREADED_DISCUSSION`. **Not for CV PDF** (different rules—no markdown word hacks, no links on CV PDF).

## Character budget (ICML-style 5000)

| Section | Share | Purpose |
|---------|-------|---------|
| Opener | 10–15% (~600) | Thanks + strengths |
| Body | 75–80% (~4000) | Must-win + pivotal reviewers |
| Closing | 5–10% (~400) | Meta line: resolved / accept path |

Verify: `scripts/count_limits.sh rebuttal.txt --chars --limit 5000`

## Markdown table trick (Cesar — OpenReview only)

Some systems count **one word per table row**. Pack new experiments as:

```markdown
| Model | M1 | M2 | M3 |
|-------|----|----|-----|
| A | 69 | 40 | 38 |
| B | 99 | 89 | 78 |
| Ours | 95 | 91 | 80 |
```

Follow with 1–2 interpretive sentences—not row-by-row prose.

**Warning:** Confirm counter behavior for your venue; ICML OpenReview may count characters differently. Always run `count_limits.sh`.

## Density tactics (EvoScientist + Devi)

| Tactic | Effect |
|--------|--------|
| Tables > prose for numbers | High |
| Bullets > paragraphs | Medium |
| @All merge for shared concerns | High |
| Q/A one-liners | High |
| One-line thanks opener | Medium |
| Link to appendix in **revised paper** (not CV PDF) | Saves chars if policy allows |

## Q/A format (Devi Tip 3)

```text
"Are masks used during training?" → No. Masks are evaluation-only.
"Why no GLORP3 eval?" → GLORP3 tests X; we evaluated on Y and Z (Table 2), which cover the same failure mode.
```

## @All consolidation

```text
**@All — Baseline under shared budget (@R1, @R3).**
[One table or 4 bullets with numbers]
@R1: see above. @R3: same table addresses your PGD concern.
```

## Red / orange / gray budget

- 60% effort on red (score-driving)
- 30% orange
- 10% gray (batch: "We thank all reviewers for typo lists; all will be fixed.")

Five deep answers beat fifteen shallow ones.

## Underscore hack (Cesar — use with caution)

`Question-2-Reviewer-3: Is_Foo_a_Bar?` — only on OpenReview text venues; abuse may get rebuttal removed.

## Condense workflow (text-condense)

When over limit after structural trims:

1. Preserve all numbers, citations, reviewer labels
2. Remove filler ("It is worth noting", "Furthermore" openers)
3. Merge duplicate sentences
4. Re-run count_limits.sh

## Niklas Elmqvist (CHI-style)

- Mirror reviewer's numbering and headings
- Brevity over elegant prose
- Facts and citations from paper beat rhetoric

## Closing four-point summary (Cesar)

End with numbered major resolutions pointing to answer anchors—helps AC scan.

## External links

- **CV PDF:** forbidden
- **OpenReview:** check anonymity rules; prefer numbers inline over "see repo" when links disallowed
