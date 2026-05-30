# Response Templates

Copy-ready patterns by concern type. Combine with [strategy-decision.md](../strategy-decision.md).

## Tracker (Issue Board)

```markdown
| ID | Rev | Sev | Concern | Action | merge_key | Status |
|----|-----|-----|---------|--------|-----------|--------|
```

Severity: `critical` | `major` | `minor` | `misunderstanding`  
Action: `CLARIFY` | `FIX-PAPER` | `NEW-ANALYSIS` | `ADAPT-BASELINE` | `ACK-LIMIT` | `CONCEDE`

## Opening (conference)

```text
We sincerely thank all reviewers for their thoughtful and constructive feedback. We are
encouraged that [Reviewers X, Y] found our [motivation/idea] [strong/clear/novel], and
[Reviewer Z] found our [experiments/analysis] [convincing/insightful]. We address every
concern below with clarifications and, where requested, additional results under fair,
shared experimental settings.
```

## Direct-answer first lines

| Question | Strong first line |
|----------|-------------------|
| Averaged across seeds? | **Yes.** We average over [k] seeds. |
| Only two gradients? | **Not quite.** We compute **O(√N)** gradients per iteration via class probing. |
| Why no PGD? | **We provide one below** under a shared [N]-pixel budget. |
| Table X and Y conflict? | **Thank you for catching this.** They reflect different [code/dtype] pipelines. |
| Why interpretable? | **Because** L0 sparsity, saliency maps, and sequential pixel updates. |

## Experimental inconsistency

```text
**[Title].** We thank the reviewer for noting [discrepancy]. [Table A] and [Table B] differ
because [exact pipeline delta]. Concretely, [numeric/dtype example]. Canonical results use
[pipeline] in [Table X, §Y]. We will revise the paper to state this explicitly and unify code paths.
```

## Fair runtime / pixel budget

```text
**Pixel budget.** [Ours] modifies [k] pixel(s)/iteration; [baseline] modifies [k'].
All methods use the same total of [B] modified pixels per sample ([dataset detail]).
```

## @All adapted baseline

```text
**@All — Baselines under shared [N]-pixel budget (@R1, @R3).**
Direct PGD/C&W comparisons mix threat models; we adapt:
- PGD-[N]px: [iter] × [px/step]
- C&W-[N]px-extrema: top-[N] pixels by |δ|

[Compact table: ASR | L2 | Time]

Under this setting, [highlight]. We will include this table in the final version.
```

## Heuristic → theory

```text
**[Heuristic name].** Our design follows [framework, e.g. soft-label CE]:
∂L/∂f_i = −ŷ_i/f_i. Empirically [tradeoff note]. We will clarify in §[X] and add [ablation pointer].
```

## Speed → impact

```text
**Practical speed.** [Method] is the first [family] feasible at [scale], enabling [security eval /
defense testing] previously infeasible due to [barrier].
```

## Acknowledge + limit

```text
We agree that [limitation] remains. [One sentence on scope.] We will state this explicitly in
§[Limitations] and view [gap] as future work.
```

## Journal — point-by-point (Nature / aether)

```text
**The editor/referee wrote:** [preserved quote]

**Our reply:** [Direct answer first.] [Evidence.] [Scientific reasoning if disagreeing.]

**Changes in manuscript:** [Section X, paragraph Y, Figure Z — or "No change; clarification only."]
```

## Journal — disagree respectfully

```text
We thank the reviewer for raising this important point. We respectfully note that [concern]
reflects [misread / different scope]. As shown in [Table X / §Y], [evidence]. To avoid future
confusion, we will [specific clarification edit].
```

## Merrie — specific commitment

Weak: "We will include the standard deviation in our revisions."  
Strong: "R2 asked for the SD of variable X; the value is 8.2; we will add it to Table 3, row 2."

## Devi — Q/A one-liner

```text
"[Reviewer question in quotes?]" → [Direct answer.] [Optional one-line evidence.]
```

## aipoch — tone boundaries

- Acknowledge before rebutting
- Separate **clarification** from **new evidence** from **manuscript edit**
- Flag `UNRESOLVED` when author input missing — do not fabricate

## Closing (conference — Cesar four-point)

```text
We focus on four major points: (1) [resolution] — see @R1; (2) [resolution] — see @All;
(3) [new result] — see @R2; (4) [claim scope] — see @R3. We thank all reviewers again.
```

## Merge map example

```markdown
| merge_key | Reviewers | Home |
|-----------|-----------|------|
| baseline-pgd | R1, R3 | @All Table 1 |
| reproducibility | R1 | R1 block lead |
```

## Chinese author notes (optional section in output)

```text
中文核对：
- [ ] 每条审稿意见均有对应回复
- [ ] 数值与论文一致
- [ ] 语气：礼貌、直接、不防御
```
