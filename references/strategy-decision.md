# Strategy and Decision

Use after Issue Board, before Draft. Goal: change the **decision path**, not win every argument.

## Audience model (Devi Parikh / Bill Freeman)

- **Primary:** Area Chair / meta-reviewer (may only read reviews + rebuttal).
- **Secondary:** Individual reviewers (especially champion and pivotal persuadables).
- Rebuttal is a debate for **judges**, not opponents.

## Reviewer stance map

| Stance | Signals | Strategy |
|--------|---------|----------|
| Champion | Score ≥7 or strong accept language | Arm with copy-pasteable arguments; don't over-defend |
| Persuadable | Borderline 4–6, "may be swayed" | Invest most effort here |
| Skeptical | Major concerns but fixable | Evidence + narrow concessions |
| Entrenched | Score ≤3, ideological reject | Answer once factually; do not over-invest |

**Zeller rule:** If no potential champion exists, acceptance odds are slim — still rebut if any reviewer is positive.

## Color-code concerns (EvoScientist)

| Color | Meaning | Effort budget |
|-------|---------|---------------|
| **Red** | Score-driving concern | ~60% |
| **Orange** | Addressable with evidence | ~30% |
| **Gray** | Minor / cosmetic | ~10% |
| **Green** | Praise | Note for opening; ammunition for champion |

Ask per reviewer: *"What would move this score to accept?"* Address the **invisible question** behind the literal comment.

## Decision path (ml-research)

1. Record scores, confidence, meta-review if any.
2. Identify **main accept path** and **main reject path**.
3. Mark **pivotal issue** and **pivotal reviewer** (`reviewer_priority: pivotal`).
4. Allocate disproportionate drafting + evidence to must-win issues.

## Response posture (pick one per issue)

| Posture | When |
|---------|------|
| `accept-and-fix` | Reviewer correct; fix feasible |
| `clarify-misunderstanding` | Already in paper; cite + restate |
| `rebut-with-evidence` | New table/number/experiment (if allowed) |
| `partially-concede` | Valid subset; narrow claim |
| `provide-new-result` | Ran targeted experiment for this concern |
| `scope-and-limit` | Honest boundary |
| `defer-to-revision` | Camera-ready only (venue allows) |
| `structural_distinction` | "Reduces to X" attack — agree locally, show preserved structure |

## Strategy table (inno-rebuttal)

| Strategy | When |
|----------|------|
| Accept and fix | Missing ablation you can run |
| Clarify misunderstanding | Content in paper but buried |
| Partial agree and narrow claim | Concern valid for subset of claims |
| Respectful disagreement | Demonstrably wrong with evidence |
| Out of scope | Legitimate but beyond paper contribution |
| Escalate to AC | Bad-faith or factual reviewer error (confidential channel only) |

When `Escalate to AC` applies, load [artifacts/official-comment.md](artifacts/official-comment.md) — draft AC-only note **after** rebuttal covers the science. Never use AC channel as a second full rebuttal (ICML policy).

## Ordering and structure

1. **Opening:** 3–5 sentences — thank; 2–3 cited strengths (@R1, @R2).
2. **Principal arguments (Grosser):** 3–5 titled conclusions answering merged major concerns (optional but strong for one-page PDF).
3. **Per-reviewer blocks** or **@All** for shared evidence.
4. **Closing:** Resolved / remaining / why accept (meta-reviewer line).

**Yao / Devi:** You control order — paraphrase comments; put strongest answers first; do not follow reviewer order blindly.

## Champion strategy (EvoScientist + Cesar)

- Real audience is often the **positive reviewer** in AC discussion.
- Make key sentences **copy-pasteable**.
- Highlight where reviewers **agree**.
- Flag **contradictions** between reviewers factually (never attack personally).

## Experiment response planning

For each `NEW-ANALYSIS` or `grounded_evidence` issue:

- Smallest credible experiment / table / proof sketch.
- Feasibility before deadline.
- Success / partial / failure wording prepared.
- Venue policy: CV discourages unrequested new results; ARR allows small responsive experiments.

## Counterintuitive principles

1. Submit rebuttal even with one strong positive + one strong negative (outlier may fold in discussion).
2. Concede something small to win credibility on big points.
3. One new experiment table beats three paragraphs.
4. Don't defend every point equally — signals you don't know what matters.
5. Prebuttal during writing (optional): draft answers to likely attacks before reviews arrive.

## Must-win vs do-not-overinvest

| Label | Rule |
|-------|------|
| must-win | Could decide acceptance if answered well |
| must-answer | Direct question; answer even if brief |
| quick-win | Easy clarification, high value |
| do-not-overinvest | Unmovable objection or low decision weight |

See [templates/response-templates.md](templates/response-templates.md) for copy-ready phrases.
