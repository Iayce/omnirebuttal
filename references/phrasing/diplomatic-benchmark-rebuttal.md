# Diplomatic Phrasing — Benchmark / Dataset Rebuttals

Use when reviewers attack **scale**, **evaluation subset**, **QC/rubric transparency**, or **collection cost**. Goal: explain without sounding defensive or insulting to the field.

## Tone rules

- **Never** say "other papers are also small" or "reviewers don't understand cost" directly.
- **Do** frame as design tradeoffs, comparable resource classes, and policy-compliant bounds.
- **Do** pair limitation with a **concrete revision** (move appendix → body, rubric matrix, release artifact).
- Prefer **one sentence** per diplomatic point — page budget is tight on `ONE_PAGE_PDF`.

## Scale vs related work (implicit comparison)

**Intent:** 898 is not tiny for *source-verified, curated meme* benchmarks; image provenance adds burden.

**Phrasing patterns (English):**

- "…which is **within the range of related curated meme resources** given the added **image-provenance burden**."
- "…a **human-curated, source-verified** corpus at this granularity, not a scrape-at-scale benchmark."

**Avoid:**

- "Other datasets are equally small."
- "Modern benchmarks are much larger than ours but they are easier."

## Evaluation subset (898 vs 200)

**Intent:** 200 is a **controlled evaluation slice**, not the dataset size; multi-model × multi-environment × multi-round retrieval is expensive.

**Phrasing patterns:**

- "The main experiments use a balanced **200-example test slice** … because each item is evaluated across **five frontier models and three environments** with **costly multi-round search/crawl calls**."
- "We will explicitly describe the **sampling rationale** so readers do not read '200' as the benchmark size."

**Avoid:**

- "We cannot afford API costs" (too raw for rebuttal).
- "Full evaluation would bankrupt us."

**Acceptable softer cost signal:**

- "disproportionately costly", "high-cost controlled slice", "expensive multi-round protocol".

## QC / rubric under-emphasized in main text

**Intent:** Material exists in supplement; main text sacrificed space, not rigor.

**Phrasing patterns:**

- "These details were **under-emphasized in the main text due to space allocation, not absence**."
- "We will **rebalance the main/supplement split** by adding a compact **Annotation and Quality Control** paragraph and moving **reviewer-relevant rubric-matrix details** into the body."

**Avoid:**

- "Reviewers should have read the appendix."
- "Page limits forced us to hide protocol."

## No-new-experiments + missing IAA / human ceiling

**Phrasing patterns:**

- "We will **not claim unreported IAA or human-ceiling numbers** in the rebuttal; we will mark broader multi-annotator calibration as **future validation**."
- "These are **bounded camera-ready changes**, not unsupported new results."

## AC-facing synthesis (closing line)

> We hope the AC sees that the main objections concern **exposition, policy-compliant limitations, and rubric transparency** rather than a flaw in the benchmark's core contribution.

Use when multiple reviewers share reproducibility/presentation concerns but praise the task and findings.

## Where this lives in Omnirebuttal

- Draft: [../artifacts/one-page-pdf-cv.md](../artifacts/one-page-pdf-cv.md) § No-new-experiments, Page-fill
- Compression: [../compression/one-page-pdf-latex.md](../compression/one-page-pdf-latex.md) § No-new-experiments compression
- Strategy: pivotal reviewer budget in [../strategy-decision.md](../strategy-decision.md)
