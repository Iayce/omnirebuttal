# EXPERIMENT_PLAN — [Venue Year, Submission ID]

> Fill after Issue Board triage, before rebuttal draft. Link each row to Issue Board IDs.
> Policy source: `VENUE_BRIEF.md` + author constraints.

## Policy snapshot

| Field | Value |
|-------|-------|
| Venue | |
| New experiments in rebuttal | prohibited / discouraged / allowed |
| Author constraint | e.g. `no-new-experiments`, API budget cap |
| Rebuttal deadline | |
| Compute note | optional |

## Summary

| Metric | Count |
|--------|-------|
| Experiment-class issues | |
| Marked `RUN` / `RUN-IF-TIME` | |
| Clarify-only (no GPU) | |
| Deferred / ACK-LIMIT | |

## Per-issue plan

| ID | Rev | experiment-class | Tier | Feasibility | Decision | Evidence / setting | Rebuttal home |
|----|-----|------------------|------|-------------|----------|-------------------|---------------|
| R2.1 | R2 | missing-baseline | C | moderate_effort | RUN-IF-TIME | Match L0 budget; PGD-196px | @All Table 1 |
| R4.3 | R4 | human-eval | D | not_realistic | DEFER | No new human study in rebuttal | §3 QC paragraph |
| … | | | | | | | |

**Decision enum:** `RUN` | `RUN-IF-TIME` | `RUN-REANALYSIS` | `CLARIFY-EXISTING` | `FIX-PAPER` | `ACK-LIMIT` | `DEFER` | `needs_user_input`

## Author confirmations

- [ ] All `RUN` rows approved by author
- [ ] All numbers in draft tagged `user_confirmed_result`
- [ ] No Tier D promises without approval

## Risks

List items that remain **残余风险** if experiments are not run (for coverage audit / 中文对照表).
