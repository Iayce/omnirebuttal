# Artifact: Journal Point-by-Point (Nature, R&R)

**Family:** `JOURNAL_POINT_BY_POINT`  
**Output:** Response letter + change checklist (+ optional revised manuscript notes).

Distilled from nature-response + aether response-to-referee.

## Default stance

- Preserve each reviewer comment faithfully before responding.
- Editor-facing verification: every concern understood, addressed, or marked unresolved.
- Map responses to manuscript evidence, revision location, justified disagreement, or `AUTHOR_INPUT_NEEDED`.
- Do not invent line numbers, figure panels, supplements, or edits.

## Task modes

| Mode | Output |
|------|--------|
| `draft` | Full point-by-point letter |
| `audit` | Gap analysis of existing draft |
| `revise` | Edit user draft |
| `triage-only` | Tracker + strategy only |
| `appeal-like` | Route separately; not default |

## ID scheme

1. Editor instructions first: `E.1`, `E.2`, …
2. Reviewers: `R1.1`, `R1.2`, `R2.1`, …
3. Flag ambiguous segmentation — do not invent reviewer boundaries

## Workflow

1. Identify decision type: minor / major / R&R / transfer / unclear
2. Classify each item: category, severity, action, missing input
3. Strategy summary before prose
4. Draft with preserved reviewer quotes (unless triage-only)
5. Map each change to section/figure/table/supplement
6. QA: completeness, traceability, tone

## Response letter anatomy (Nature-style)

```text
Response strategy summary
- Decision type / posture / major risks

Comment-response tracker
| ID | Concern | Type | Severity | Action | Missing input |

Draft point-by-point response letter

Manuscript change checklist
- [ ] specific edits

Missing information / risk flags

中文核对 (optional)
```

## Three-part block (optional LaTeX — aether)

For each comment:

```text
### R1.2 — [short title]

**The referee wrote:** [preserved quote]

**Our reply:** [direct answer + evidence]

**Changes:** [§X, p.Y, Fig.Z — or "No manuscript change; clarification only"]
```

Two-gate approval: (1) response document, (2) manuscript edits — never claim changes without author consent.

## Action mapping

| Action | Letter behavior |
|--------|-----------------|
| CLARIFY | Point to existing text; offer clearer wording for revision |
| CONCEDE + FIX | Acknowledge + exact change location |
| DISAGREE | Acknowledge concern → scientific reason → evidence |
| NEW ANALYSIS | Report results; map to figure/table in revision |
| AUTHOR_INPUT_NEEDED | Explicit placeholder |

## Tone

- Acknowledge before disagreeing
- Consider whether presentation caused misunderstanding
- Potentially public artifact — professional traceability

## QA additions

- [ ] Every reviewer comment answered or explicitly unresolved
- [ ] No invented page/line numbers
- [ ] Package readiness state set
- [ ] Editor instructions prioritized

## Relation to conference rebuttal

Do **not** use one-page CV compression tactics (no @All PDF table hacks). Journal letters may be longer and require complete point-by-point coverage.

Templates: [../templates/response-templates.md](../templates/response-templates.md) § Journal.
