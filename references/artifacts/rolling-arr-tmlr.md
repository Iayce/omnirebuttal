# Artifact: Rolling Revision (ARR, TMLR)

**Family:** `ROLLING_REVISION`  
**Output:** Short author response + revision plan for next manuscript version.

## ARR constraints

- Text response in OpenReview-style discussion
- **No images or external links** in author response
- Small directly responsive experiments allowed
- Large new results discouraged
- Long adversarial back-and-forth low value — resolve and move on

## TMLR constraints

- Public discussion
- Authors respond within ~2 weeks after third review (typical)
- Emphasize what will change in next revision
- Technically productive exchanges over rhetoric

## Shift in mindset

| Conference rebuttal | Rolling revision |
|-------------------|------------------|
| Win AC this cycle | Clarify + plan next version |
| Dense one-page fight | Core issue resolution |
| Many new numbers | Targeted fixes + revision map |

After first response round, pivot to **revision plan mode** (inno-rebuttal Stage 6).

## Response structure

```text
1. Thank reviewers and AE/editor
2. Global: 2–3 core resolutions
3. Point-by-point (concise) for major items only
4. Revision plan section:
   - Changes committed for next version
   - Timeline / scope
   - Items deferred with rationale
```

## Issue Board emphasis

| Priority | Action |
|----------|--------|
| Soundness / reproducibility | Must resolve or narrow claims |
| Missing baseline | Add to revision plan with experiment slot |
| Presentation | Brief acknowledge + fix in next PDF |
| Entrenched disagreement | One clear summary; stop after 2 rounds |

## REVISION_PLAN (required)

```markdown
## Next version changes
- [ ] R1.2: Add baseline X to Table 2 — experiment scheduled
- [ ] R2.1: Threat model paragraph §2 — text drafted
- [ ] Limitation on Y — §5

## Deferred
- R3.4: Theoretical convergence proof — future work (scope)
```

## Compression

Use [../compression/text-budget-markdown.md](../compression/text-budget-markdown.md) — prose density, no large figures in ARR response.

## Follow-up

- ARR: resubmit or commit to venue with meta-review
- TMLR: continue public thread until acceptance or withdraw

## QA additions

- [ ] No disallowed links/images (ARR)
- [ ] Revision plan concrete, not vague promises
- [ ] Long threads trimmed to technical substance
