# Visual Density Patterns

Cross-venue evidence presentation. Choose format by information type and space budget.

## Decision tree: table vs figure

```
Need to show numeric comparison?
├─ ≤4 columns AND ≤6 rows → compact TABLE (booktabs / markdown)
├─ Many methods OR many metrics → grouped BAR chart
├─ Trend across scale/dataset → line plot or sparkline
├─ Pipeline/setup difference → small block DIAGRAM (boxes + arrows)
└─ Single scalar answer → bold number in prose + one-line context
```

## Pattern catalog

| Scenario | Preferred | Avoid |
|----------|-----------|-------|
| Multi-baseline ASR/Acc | 5×4 table or grouped bars | Paragraph per method |
| Ablation 3–4 variants | Horizontal bar, single metric | Repeated method descriptions |
| Matched budget comparison | One @All table (playbook) | Three copies for R1/R2/R3 |
| Runtime vs accuracy | Dual-axis or two-column mini chart | Long runtime prose |
| Implementation pipeline diff | 3-box diagram (GPU sum vs CPU sum) | Half-page explanation |
| Already in paper | Cite Table X + restate 1 row | "See Section 3" only |

## Table design (minimal)

- Header row only; no redundant units in every cell
- Use `%` or `ms` in column header, not each cell
- Bold best-in-column only if not misleading
- For rebuttal PDF: `\small` + `booktabs`

## Figure design (minimal)

- One message per figure; short caption states takeaway
- Width: 0.8–0.9 `\linewidth` single column; `figure*` only for @All critical evidence
- Label methods consistently with paper (abbreviations in caption if needed)
- Color: readable in grayscale if printed

## Table → figure examples

**Before (prose):** "Method A achieves 82.1%, Method B 99.2%, Ours 95.4% on Metric1…"

**After (table):** 4-row table as in text-budget-markdown.md

**After (figure):** Grouped bar, 3 methods × 2 metrics, caption: "Under 196px budget, ours trails B on M2 but leads on ASR (M1)."

## Multi-reviewer reuse

| Wrong | Right |
|-------|-------|
| Same table in R1, R2, R3 sections | One @All table + "See @All" pointers |
| Figure per reviewer | One figure, multiple textual pointers |

## When NOT to add visuals

- Venue forbids figures (some text-only discussion periods)
- Visual would be smaller/mless readable than a 4-line table
- Data not yet `user_confirmed_result` (Provenance gate)

## FastJSMA reference

Adapted PGD/C&W table under unified pixel budget — see [../cases/fastjsma-iccv2025.md](../cases/fastjsma-iccv2025.md).

LaTeX snippets: [one-page-pdf-latex.md](one-page-pdf-latex.md).
