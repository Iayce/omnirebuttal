# Experiment Rebuttal Router

Reviewers **often request new experiments** even when venues **implicitly or explicitly discourage** substantial rebuttal-time work. Omnirebuttal must route each experiment ask to: **run now**, **reanalyze existing artifacts**, **clarify from paper/appendix**, **bounded camera-ready promise**, or **respectful deferral** — never invent numbers.

**Prerequisite:** `VENUE_BRIEF.md` must record `New experiments in rebuttal: prohibited | discouraged | allowed | ambiguous` plus any **author hard constraint** (e.g. `no-new-experiments`, compute/API budget).

**Related:** [strategy-decision.md](strategy-decision.md), [safety-gates.md](safety-gates.md), [phrasing/diplomatic-benchmark-rebuttal.md](phrasing/diplomatic-benchmark-rebuttal.md), [cases/fastjsma-iccv2025.md](cases/fastjsma-iccv2025.md).

---

## Why this module exists

| Fact | Implication |
|------|-------------|
| CV PAMI-TC motion: reviewers should not request **substantial** rebuttal experiments | Authors can cite policy when declining major new work |
| ICLR / NeurIPS: new results **allowed** but should **clarify** existing submission, not rewrite the paper | Small scoped runs OK; frame as validation |
| Reviewers still ask for baselines, ablations, human studies, larger eval | Triage must label each ask `experiment-class` and pick a posture |
| One new table often beats three paragraphs (EvoScientist / Devi) | If you **can** run Tier A–B cheaply, prioritize score-driving asks |
| FastJSMA ICCV: adapted baselines under **matched budget** flipped borderline → accept | Reframe unfair comparisons instead of refusing outright |

Distilled from: CVPR 2025 Author/Reviewer Guidelines, ICLR/NeurIPS reviewer FAQ, EvoScientist `paper-rebuttal`, chtc66 `review-rebuttal`, Henryhe09 `review2rebuttal`, live ACM MM practice.

---

## Workflow (after Issue Board, before Draft)

1. **Extract** every reviewer item that implies new numbers (baseline, ablation, human eval, larger test set, statistical test, new backbone, new dataset).
2. **Classify** each with `experiment-class` (below) and `feasibility` (below).
3. **Record** decisions in `EXPERIMENT_PLAN.md` (template: [templates/experiment-plan-template.md](templates/experiment-plan-template.md)).
4. **Get author confirmation** for any item marked `RUN` or `RUN-IF-TIME` before putting numbers in paste-ready rebuttal.
5. **Draft** using posture: show table now (`user_confirmed_result`) OR evidence inventory OR honest deferral.

Do **not** auto-run GPU jobs from this skill unless the user explicitly asks.

---

## Venue policy quick reference

| Venue family | Official posture (typical) | Author strategy |
|--------------|---------------------------|-----------------|
| **CV one-page PDF** | Reviewers discouraged from **substantial** new experiments; authors discouraged from **unrequested major** new results; **small** experiments if reviewer asked and feasible | Tier A–C only; one compact table; no new contribution narrative |
| **ICLR / NeurIPS threaded** | New results **allowed**; rebuttal clarifies questions; **original submission** remains decision basis | Targeted Tier B–C for pivotal reviewer; markdown table for density |
| **ICML per-review text** | Prioritize major misunderstandings; char budget tight | One table per must-win reviewer max |
| **ACM MM** (check brief) | Often **no new experiments** in rebuttal; clarification + revision | Strong `no-new-experiments` branch; existing appendix evidence |
| **ARR / rolling** | Small **responsive** experiments OK | Plan for next revision if not runnable now |
| **Journal R&R** | Experiments often **expected** in revision | `RUN` or explicit revision timeline with `approved_for_rebuttal` |

Always prefer live `VENUE_BRIEF.md` over this table.

---

## Decision tree (per issue)

```
Reviewer asks for experiment / numbers
        │
        ├─ Already in paper / supplement / logs?
        │     └─ YES → CLARIFY + cite (Table X, Appendix Y); optional tiny reformat table
        │
        ├─ Tier A reanalysis only (no new forward passes)?
        │     └─ YES → RUN-REANALYSIS; show table in rebuttal if done
        │
        ├─ Author / venue = no-new-experiments?
        │     └─ YES → ACK-LIMIT + evidence inventory + camera-ready plan
        │              (see one-page-pdf-cv.md § No-new-experiments)
        │
        ├─ Request is "substantial" (major-revision scope)?
        │     └─ YES → DEFER / OUT-OF-SCOPE + cite venue policy + offer camera-ready
        │
        ├─ Feasible Tier B–C before deadline + pivotal reviewer?
        │     └─ YES → RUN (author confirms) → one table in rebuttal
        │
        └─ Else → PARTIAL-CONCEDE + bounded revision OR honest limitation
```

**Substantial** (CVPR reviewer guide sense): what would normally belong in a **major revision**, not a ~1-week rebuttal — new dataset collection, full human study, re-implementing unavailable SOTA from scratch, exhaustive hyperparameter sweep.

---

## Experiment tiers

| Tier | Description | Typical cost | Rebuttal treatment |
|------|-------------|--------------|-------------------|
| **A — Reanalysis** | Reslice existing logs, seeds, cached preds; recompute stats | Hours | Strongly prefer; show table |
| **B — Minimal add-on** | One ablation / one backbone / one metric on existing pipeline | ≤1–2 GPU-days | Run if pivotal; compact table |
| **C — Adapted comparison** | Reframe baseline under **matched budget** (FastJSMA PGD/C&W pattern) | Medium | Run if reviewer claims unfair comparison |
| **D — New data / human study / large sweep** | New annotation, human ceiling, full benchmark rerun | High | Defer unless journal R&R or author insists |

**Rule:** One Tier B/C table addressing a **red-tier** concern beats three paragraphs (EvoScientist). Do not scatter the same table across three reviewers — use `@All`.

---

## Feasibility labels (review2rebuttal)

| Label | Meaning | Default rebuttal posture |
|-------|---------|--------------------------|
| `ready_now` | Codepath + data exist; author can run today | `RUN` after confirm |
| `moderate_effort` | Needs config tweak or short job queue | `RUN-IF-TIME` or split: partial now + rest camera-ready |
| `high_risk` | May not finish or may fail silently | Do not promise; outline plan only |
| `not_realistic` | Violates deadline, budget, or venue policy | `ACK-LIMIT` / `DEFER` with policy anchor |
| `unknown` | Repo/data not inspected | `needs_user_input`; no fabricated feasibility |

---

## experiment-class taxonomy

| Class | Examples | First move |
|-------|----------|------------|
| `missing-baseline` | PGD, C&W, SOTA method X | Adapt under shared budget (C) or explain inapplicability |
| `missing-ablation` | Remove module Y | Tier B if one forward pass |
| `unfair-comparison` | Different pixels/iter, unmatched compute | Clarify protocol + optional matched table |
| `scale-eval` | More samples, full benchmark | Clarify 898 vs 200; defer full run (diplomatic phrasing) |
| `human-eval` | IAA, human ceiling | Usually defer; never invent κ |
| `statistical` | Significance, CI, seeds | Tier A if logs exist; else defer |
| `new-setting` | New dataset, OOD, new modality | Usually Tier D defer |
| `reproducibility` | Hyperparams, prompts, code | CLARIFY + release plan; not always GPU |

Map Issue Board `action`:
- `NEW-ANALYSIS` → only when venue allows + feasibility ≥ `moderate_effort` + author confirms
- Otherwise → `CLARIFY`, `ADAPT-BASELINE`, `ACK-LIMIT`, `FIX-PAPER`

---

## Reporting in rebuttal

### Do (Merrie / Devi)

- Put **numbers in the rebuttal** (table, equation, corrected row) then say paper will update.
- State **exact setting**: data split, budget, metric, seed count.
- For Tier C: lead with **what was matched** (pixels, steps, API calls, wall-clock if relevant).
- Tag source: `user_confirmed_result` in Issue Board.

### Don't

- "We will add experiments" with no setting and no numbers.
- Claim full benchmark when only a subset ran.
- Use cost/API spend as **primary** excuse (safety-gates); use **scope / venue policy / feasibility** instead.
- Run unrequested **major new contribution** on CV PDF (reviewers told to disregard).

### Partial / null results

If an experiment was run but inconclusive:

> We ran [setting] as suggested. Under this budget, [metric] moved from X to Y (Δ small). We therefore narrow the claim to […] and add this table to the revision.

Honest null beats silent omission.

---

## Push-back patterns (respectful)

**Out of scope for rebuttal window:**

> We agree [X] would strengthen the paper. A full [X] requires [scope], which exceeds what is feasible in the rebuttal period. We will include [bounded version] in the camera-ready / revision and clarify the limitation here: [one sentence].

**Unavailable baseline (CVPR 2024 re-implementation guidance):**

> [Method X] has no public code/checkpoint; re-implementation in the rebuttal window would not be a fair or reproducible comparison. We instead compare to [Y, Z] under [matched protocol] and add [adapted baseline] where feasible (Table N).

**Reviewer asks for human ceiling / IAA (benchmark papers):**

> We do not report unverified human-ceiling or IAA numbers in the rebuttal. We will add [protocol detail / rubric transparency] in the revision and treat broader human calibration as future validation.

---

## Integration with no-new-experiments mode

When author cannot run **any** new GPU/API work:

1. Still complete `EXPERIMENT_PLAN.md` — mark all items `not_realistic` or `deferred_camera_ready`.
2. For each experiment ask, pick one:
   - evidence already in supplement
   - bounded `FIX-PAPER` (protocol, rubric, figure)
   - `ACK-LIMIT` with diplomatic scale/cost phrasing
3. Never fabricate to " satisfy" the reviewer.

See [artifacts/one-page-pdf-cv.md](artifacts/one-page-pdf-cv.md) § No-new-experiments.

---

## QA gates (experiments)

Before paste-ready output:

- [ ] Every `NEW-ANALYSIS` issue has `feasibility` + author decision in `EXPERIMENT_PLAN.md`
- [ ] Every number in rebuttal tagged `user_confirmed_result` or `paper` / `review`
- [ ] No Tier D promised without explicit author approval
- [ ] Venue policy cited when declining substantial requests (once, not repetitively)
- [ ] At most **1–2** new tables on one-page PDF unless user confirms space

---

## Distilled external sources

| Source | Pattern absorbed |
|--------|------------------|
| CVPR 2025 Author/Reviewer Guidelines | No substantial rebuttal experiments; unrequested major results disregarded; small OK |
| ICLR 2025/2026 Reviewer Guide | Additional experiments allowed if limited scope, validate existing results |
| NeurIPS FAQ | New results OK; original submission is basis; clarify only |
| EvoScientist `paper-rebuttal` | One experiment table > paragraphs; color-code experiment asks |
| chtc66 `review-rebuttal` | Split 必须补实验 vs 澄清项; never fake completed experiments |
| review2rebuttal | Feasibility categories; conservative planning; author gates |
| FastJSMA ICCV case | Adapt baselines under matched budget; run analysis gaps |
