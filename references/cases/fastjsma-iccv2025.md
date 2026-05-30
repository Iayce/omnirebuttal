# Case Study: FastJSMA @ ICCV 2025 (#11200)

## Outcome

| Stage | R1 (4XMx) | R2 (LRfV) | R3 (Nevp) | Total | Meta |
|---|---|---|---|---|---|
| Pre-rebuttal | 3 (BR) | 4 (BA) | 4 (BA) | 433 | Borderline |
| Post-rebuttal | 4 (BA) | 4 (BA) | 5 (WA) | 554 | **Accept** |

Meta-review quote: *"initially received a borderline ranking, which was subsequently upgraded to a positive one after the rebuttal."*

R1 final note: rebuttal addressed reproducibility and methodology; still noted baseline/theory limits but inclined to accept.

R3 final note: *"provided additional results as requested... quite convincing, so I am raising my score."*

## Initial reviewer landscape

### R1 (4XMx) — Borderline Reject (highest risk)

**Strengths:** elegant approximation, interpretability, ImageNet scale, good ablation.

**Major concerns:**
1. Table 1 vs Table 2 inconsistency (ASR 43.98% / 339µs vs 37.66% / 26,298µs)
2. Unclear pixels modified per iteration → unfair runtime comparison
3. Virtual labels lack theory/empirics
4. max_attempt=10 only shown for CIFAR-10; scalability unclear
5. No PGD/C&W baselines

**Minor:** normalized Fig. 2, gradient scaling, "attempt class" vs untargeted confusion.

### R2 (LRfV) — Borderline Accept

**Major:** speed advantage not tied to practical scenarios (defense, real-time).

**Minor:** threat model undefined; ImageNet lacks non-JSMA comparisons.

### R3 (Nevp) — Borderline Accept (low confidence)

**Major:** explain JSMA "interpretability"; compare to non-JSMA methods.

**Minor:** JSMA Eq. missing sign checks/abs; gradient count O(√N) vs "two gradients"; table bolding; language in §3.5.

## Internal triage (CN_reply.md + mentor advice)

Authors mapped each concern to Q IDs and brainstormed responses.

**Mentor strategy (critical):**
1. **Analysis gaps** → run the requested analysis and report numbers
2. **PGD/C&W comparison** → do not compare naively; argue different perturbation constraints; **adapt** PGD/C&W to JSMA-style L0 budget, then compare under identical settings

Author notes also flagged:
- Table inconsistency: own the bug, explain AMP/GPU-CPU pipeline difference
- Fig. 2 normalization: revise or explain space limits
- ImageNet PGD experiment if compute allows

## What the submitted rebuttal did (rebuttal.tex)

### Opening
Thanked reviewers; highlighted strong motivation, clarity, novelty (R1, R2), insightful analysis (R3).

### @R1 (4XMx) — longest block

**Experimental inconsistency:**
- Ablation/Fig. 2 used modified code: g⁺ and g⁻ summed on CPU after separate GPU→CPU transfer
- Main Table 1: sum on GPU, then single transfer (faster, more stable)
- Explained bf16 vs fp16 cancellation example for ASR drop
- Committed to paper clarification for reproducibility

**Pixel modification:** FastJSMA 1 px/iter; JSMA 2 px/iter; same total pixel budget.

**Virtual labels:** Soft-label CE framing; gradient −ŷᵢ/f(x)ᵢ; √N perturbation accelerates attack.

**max_attempt:** √N sampling works on large datasets (empirical).

**Minor items:** add raw metrics; explain g⁻×N scaling; clarify "attempt class" ≠ targeted attack.

### @R2 (LRfV)

**Speed in practice:** First JSMA-style attack practical on ImageNet → enables security eval and real-time defense testing.

**Threat model:** White-box; will state explicitly.

### @R3 (Nevp)

**Interpretability:** L0 sparsity, Jacobian saliency maps, sequential single-pixel updates preserved.

**Format/language:** unify table bolding; polish §3.5.

**JSMA formula:** full corrected S(x,t)[i] with sign checks and absolute values (Papernot Eq. 8).

**Gradient count:** O(√N) gradients per iteration, not just two.

### @All — baseline table (ImageNet, 196 px budget)

| Method | ASR (%) | L2 | Time (µs) |
|---|---|---|---|
| FastJSMA | **54.89** | **9.19** | 7,908 |
| PGD-196px | 14.84 | 0.18 | **2,744** |
| C&W-196px-extrema | 39.92 | 10.22 | 477,270 |

Setup: PGD 2 iter × 98 px; C&W top-196 |δ| pushed to extrema. Unified L0-style budget.

## Why it worked

1. **Highest-risk issue first** — reproducibility answered with mechanistic detail, not hand-waving
2. **Shared baseline concern solved once** — one table for R1, R2, R3
3. **Adapted baselines** — turned "unfair comparison" objection into a strength
4. **Show don't tell** — corrected JSMA equation and comparison table in rebuttal body
5. **Positive opening + color tags** — AC sees strengths and organized coverage
6. **R3 score lift** — new results explicitly requested and delivered convincingly

## Artifacts in project folder

| File | Role |
|---|---|
| `comments.md` | Raw reviewer text |
| `CN_reply.md` | Bilingual triage + brainstorm + mentor notes |
| `rebuttal_guide.md` | Devi Parikh principles + examples |
| `rebuttal.tex` | Final one-page rebuttal |
| `finaldecision.md` | Acceptance letter + final reviews |
| `sec_new/4_exp.tex` | Revised experiments (post-rebuttal paper state) |
