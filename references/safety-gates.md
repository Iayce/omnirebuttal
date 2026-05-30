# Safety Gates

Three hard gates — if any fails, **do not finalize** paste-ready output.

## Gate 1 — Provenance

Every factual claim must trace to:

| Source tag | Meaning |
|------------|---------|
| `paper` | In submitted manuscript (cite section/table/line) |
| `review` | Verbatim reviewer claim |
| `user_confirmed_result` | Author supplied new number/experiment |
| `user_confirmed_derivation` | Author supplied proof/sketch |
| `future_work_only` | Explicitly labeled planned work |

No source → remove claim or mark `AUTHOR_INPUT_NEEDED`.

**Never invent:** experiments, ASR/accuracy numbers, citations, reviewer quotes, section numbers, figure panels.

## Gate 2 — Commitment

Every promise maps to:

| Commitment | Rule |
|------------|------|
| `already_done` | Change exists or number is in draft |
| `approved_for_rebuttal` | Authors explicitly approved this promise |
| `future_work_only` | Camera-ready / revision; labeled as such |

**Merrie rule:** Prefer showing the actual paragraph, equation, or statistic in the rebuttal—not "we will add statistics."

If rebuttal says "we updated Table 2," verify Table 2 change is real or tracked in `REVISION_PLAN`.

CV venues: unrequested major new contributions may be disregarded by reviewers—tag and minimize.

## Gate 3 — Coverage

Every Issue Board item ends as:

| End state | Meaning |
|-----------|---------|
| `answered` | Response in draft with anchor |
| `deferred_intentionally` | Explicit one-line reason |
| `needs_user_input` | Blocked; flagged to author |

No issue may **silently disappear**. All `critical` and `major` items must reach `answered` or documented deferral.

## Cross-review consistency

- Same `merge_key` → one canonical answer; other reviewers get pointer.
- No contradictory claims to R1 vs R3 on the same fact.

## Tone red lines

- No "reviewer failed to understand" / "obviously wrong."
- Prefer "**Not quite.**" + data.
- No hostile, sarcastic, or accusatory language.
- No citing time/money as primary reason to skip requested science (explain scope instead).

## Anonymity and policy

- CV PDF: no external links; no deanonymizing URLs.
- Double-blind: no author names, lab URLs, or identifiable preprints unless allowed.
- ARR: no images or external links in author response.

## REVISION_PLAN linkage

Every manuscript-edit promise in the rebuttal must appear as a checklist item:

```markdown
- [ ] (R1-C2) Add assumption hierarchy to §3.1 — approved_for_rebuttal
```

Orphan promises = Commitment gate failure.

## Playbook anchor

**Don't promise—do.** Put table, formula, or corrected equation in rebuttal; then state paper will be updated.
