# Triage and Issue Board

Atomize every reviewer comment **before** drafting. One paragraph may contain several independent issues.

## Issue Board schema

| Field | Description |
|-------|-------------|
| `issue_id` | e.g. `R1-C2`, `R2-Q1`, `E.1` (editor) |
| `reviewer` | R1, R2, AC, Editor, Meta |
| `round` | initial / followup-1 / … |
| `raw_anchor` | Short verbatim quote (≤25 words) |
| `paraphrase` | Your one-line summary of intent |
| `category` | novelty, soundness, baseline, ablation, clarity, reproducibility, theory, limitation, ethics, presentation, question |
| `severity` | critical / major / minor / misunderstanding |
| `reviewer_stance` | champion / persuadable / skeptical / entrenched / unknown |
| `reviewer_priority` | standard / **pivotal** (borderline + addressable + high leverage) |
| `action` | CLARIFY, FIX-PAPER, NEW-ANALYSIS, ADAPT-BASELINE, ACK-LIMIT, CONCEDE, DEFER |
| `response_mode` | direct_clarification, grounded_evidence, narrow_concession, future_work_boundary, structural_distinction |
| `merge_key` | Shared ID if multiple reviewers raise same concern (e.g. `baseline-pgd`) |
| `evidence_source` | paper, review, user_confirmed_result, needs_experiment, needs_user_input |
| `status` | open / answered / deferred / needs_user_input |

## Severity guide

| Level | Definition | Budget share |
|-------|------------|--------------|
| critical | Can single-handedly cause reject (soundness, reproducibility crisis) | First |
| major | Significant but resolvable with evidence or revision | High |
| minor | Clarity, typos, formatting | One line or batch |
| misunderstanding | Paper already addresses; reviewer missed it | Clarify + cite + restate |

## Action labels

| Action | Use when |
|--------|----------|
| `CLARIFY` | Already in paper or setup misunderstood |
| `FIX-PAPER` | Will revise manuscript (specify section) |
| `NEW-ANALYSIS` | Venue allows + reviewer asked; run and report numbers |
| `ADAPT-BASELINE` | Reframe comparison under shared constraints |
| `ACK-LIMIT` | Honest scope limit + future work |
| `CONCEDE` | Reviewer is correct; narrow claim or fix |
| `DEFER` | Out of scope or impossible before deadline |

## Tracker template

```markdown
| ID | Rev | Sev | Concern | Action | merge_key | Status |
|----|-----|-----|---------|--------|-----------|--------|
| R1.1 | R1 | critical | Table 1 vs 2 ASR mismatch | CLARIFY+FIX | — | open |
| R1.5 | R1 | major | No PGD/C&W baseline | ADAPT-BASELINE | baseline-pgd | open |
| R3.2 | R3 | major | Non-JSMA comparisons | ADAPT-BASELINE | baseline-pgd | open |
```

## Triage workflow

1. **Extract** all comments per reviewer (preserve wording).
2. **Atomize** — split compound paragraphs into single concerns.
3. **Paraphrase intent** — what does the reviewer really worry about?
4. **Cluster** — assign `merge_key` for duplicates across reviewers.
5. **Score severity** — reproducibility > missing baseline > unclear method > presentation.
6. **Mark pivotal reviewers** — low/borderline score + addressable concerns + high confidence.
7. **Label action + response_mode** per issue.
8. **Order** — critical with strong answers first; batch minors last.

## Venue-specific field mapping

| Venue form | Map to |
|------------|--------|
| NeurIPS: Questions, Limitations | Separate issues each |
| ICML: Weaknesses + Questions | Split bullets |
| ICLR: Strengths/Weaknesses | Weaknesses → issues; Questions → must-answer |
| ARR: Weaknesses, Comments/Suggestions | Split; track reproducibility score separately |

Optional: RebuttalStudio stage1 skills provide venue-specific breakdown hints (external).

## Merge map (required before draft)

```markdown
| merge_key | Reviewers | Single response home |
|-----------|-----------|----------------------|
| baseline-pgd | R1, R3 | @All table |
| threat-model | R2 | R2 block |
```

Every issue must map to exactly one response location in the draft.

## QUICK_MODE exit

If user only wants analysis: output Issue Board + merge map + strategy summary; stop before Draft.
