# Reviewer Coverage Audit (Pre-Submit)

Run **after Draft + Compress**, before final QA. Ensures every reviewer concern has a traceable response and surfaces **score-lift gaps**.

## Outputs

1. **Internal:** extended Issue Board (already from triage).
2. **User-facing (optional):** Chinese or English **reviewer × concern × response** table for author sign-off.
3. **Submit package:** confirm rebuttal PDF/text covers all `critical` + `major` IDs.

## Workflow

1. From Issue Board, list **every atomized concern** per reviewer (R1–Rn).
2. For each row, map:
   - **审稿意见** — paraphrase in plain language (中文 OK for author review).
   - **回应位置** — rebuttal paragraph #, `@All` block, or thread ID.
   - **回应的意思** — one sentence: clarify / concede / fix-paper / ack-limit / cite-fix.
   - **提分备注** — `强覆盖` | `已覆盖` | `保守覆盖` | `残余风险`.
3. Add **策略摘要** (3 rows max):
   - 最可能提分对象 (borderline + champion-leaning)
   - 最需要止损对象 (Weak Reject + factual gaps)
   - 最难扭转对象 (Reject + entrenched)
4. Cross-check against compiled rebuttal (PDF text extract or char count).

## Score-lift heuristics

| Reviewer signal | Invest in rebuttal? | Typical posture |
|-----------------|---------------------|-----------------|
| Borderline + praises core idea | **Yes — pivotal** | Arm champion; copy-pasteable AC lines |
| Weak Reject + fixable exposition | **Yes** | Visible fixes (citations, QC/rubric, scale clarification) |
| Reject + only reproducibility | **Medium** | Foreground appendix + revision plan; may not flip alone |
| Entrenched + score 1–2 | **Low** | Answer once; don't burn page budget |

## Template (Markdown — author sign-off)

```markdown
## 提分策略摘要

| 类型 | Reviewer | 策略 |
|------|----------|------|
| 最可能提分 | R2, R3 | … |
| 最需要止损 | R4, R5 | … |
| 最难扭转 | R1 | … |

## 逐条对照

| 审稿人 | 审稿意见 | 回应位置 | 回应的意思 | 备注 |
|--------|----------|----------|------------|------|
| R1 / gDaV | 主实验只有 200 样本 | 第 2 段 | 898 是 benchmark；200 是 controlled slice | 重点覆盖 |
| … | … | … | … | … |
```

For large tables, prefer a **Cursor Canvas** (`.canvas.tsx` in project `canvases/`) over dumping 30+ rows into chat.

## Coverage rules

- Every `critical` and `major` Issue Board ID → at least one rebuttal anchor.
- Every `merge_key` cluster → **single home** (no duplicate scattered answers).
- Praise from reviewer → cited in opening ( ammunition for champion ).
- Items marked `残余风险` → listed in `AUTHOR_INPUT_NEEDED` or `Risk flags` (IAA, human ceiling, new experiments).

## Link to QA

Final gate: [qa-checklist.md](qa-checklist.md) — Reviewer coverage audit section.
