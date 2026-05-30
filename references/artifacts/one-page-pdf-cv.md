# Artifact: One-Page PDF (CVPR / ICCV / ECCV)

**Family:** `ONE_PAGE_PDF`  
**Output:** `rebuttal.tex` → single-page PDF via official author kit template.

**Provenance:** FastJSMA @ ICCV 2025 (433→554, borderline→accept). See [../cases/fastjsma-iccv2025.md](../cases/fastjsma-iccv2025.md).

**Compression:** [../compression/one-page-pdf-latex.md](../compression/one-page-pdf-latex.md), [../compression/visual-density-patterns.md](../compression/visual-density-patterns.md).

## Default stance

- AC may only read reviews + rebuttal → **self-contained**.
- Debate for judges, not opponents — conversational, firm, fair.
- **Don't promise—do.** Table/formula in rebuttal first; then paper update note.
- Every concern answered; missing one point worse than weak answer.
- Shared concerns → `@All` + one compact table/figure.
- Tag reviewers (`@R1`, `@R2`) or `\textcolor{rev1}{...}` for navigation.

## Document structure

### Option A — Classic (playbook)

```text
1. Opening (3–5 sentences): thank; 2–3 praised strengths (@R1, @R2)
2. Per-reviewer blocks: quote → direct answer → evidence
3. @All consolidated: shared concerns + one table/figure
4. Optional: brief revision note (after substance)
```

### Option B — Principal Arguments (Grosser + compression)

```text
1. Opening (≤4 sentences)
2. 3–5 \paragraph{Conclusion-first titles} with bullets (@Rx tags)
3. @All table/figure for merged evidence
4. Short per-reviewer remaining items (only non-merged)
5. One-line revision summary
```

Use Option B when space is tight; Option A when reviewer-specific quotes are legally/ politically necessary.

## Core tactics (FastJSMA)

### 1. Reproducibility crises

Acknowledge discrepancy → exact pipeline delta (dtype, GPU/CPU, AMP, summation order) → numeric example → anchor canonical table → paper fix commitment.

### 2. Adapt baselines (don't refuse)

Acknowledge gap → explain threat-model mismatch → adapt PGD/C&W to shared L0 budget → small table (ASR, L2, Time) → honest tradeoffs (speed vs ASR).

### 3. Fair timing comparisons

State **pixels per iteration** vs **total budget** per method explicitly.

### 4. Lightweight theory for heuristics

Connect heuristic to known framework (e.g. soft-label CE) + one-line gradient + empirical tradeoff.

### 5. Presentation nits

Show corrected equation in rebuttal; list §/Eq. edits; thank reviewer.

### 6. Speed → capability

Tie speed to new feasible evaluation regime, not abstract FLOPs.

### 7. Consolidate and color-code

Merge R1+R3 baseline requests into `@All`.

## Comment-type cheat sheet

| Concern | First line | Evidence |
|---------|------------|----------|
| Conflicting numbers | "Thank you for catching this. The difference comes from …" | Pipeline diff, dtype example |
| Unfair runtime | "We modify **k** px/iter; baseline **k'**; matched total budget …" | Pixel budget table |
| Missing baseline | "Under **shared N-pixel budget** …" | Adapted baseline table |
| Heuristic unjustified | "Virtual labels follow soft-label CE; gradient …" | One-line math |
| Threat model | "**White-box**; we will state in §…" | One sentence |
| Writing / notation | "We revise Eq. (2) as follows:" | Full corrected equation |

Full copy-ready patterns: [../templates/response-templates.md](../templates/response-templates.md).

## What NOT to do

- Hide implementation bugs — explain and fix narrative
- "Reviewer is wrong" without data → "**Not quite.**" + numbers
- Unrequested major new contributions (venue policy)
- Same experiment scattered across three answers — one @All home
- Lead with typos when reproducibility is on the line
- External links (forbidden on CV rebuttal PDF)

## QA (this artifact)

- [ ] Compiles to 1 page
- [ ] Official template unchanged
- [ ] @All table for merged major concerns
- [ ] Print-legible figures
- [ ] Every Issue Board ID addressed

## Phrases

Opening template:

> We sincerely thank all reviewers for their thoughtful feedback. We are encouraged that [strength 1] (@R1, @R2), [strength 2] (@R3). Below we address every concern with clarifications and, where requested, additional results under fair, shared settings.
