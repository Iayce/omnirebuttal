# Artifact: Official Comment & AC-Only Notes

**Not a substitute for rebuttal.** A separate channel for meta-communication with chairs — when the venue allows it and the situation warrants it.

## Terminology (OpenReview-heavy venues)

| Term | Typical meaning | Audience |
|------|-----------------|----------|
| **Author Rebuttal** | Primary response to reviews | Reviewers + AC (+ often public) |
| **Official Comment** | Structured comment on submission forum | Readers set by venue (dropdown) |
| **Confidential / AC-only note** | Restricted readers (SAC, PC, AC only) | Chairs, not reviewers |
| **Meta-review** | Written by AC | Authors see after decision (usually) |

Venues configure invitations differently — **confirm in `VENUE_BRIEF.md`** before posting.

## When to draft an Official Comment (or AC-only note)

Use the **public rebuttal** for substantive science. Use Official Comment / AC channel only when:

| Situation | Channel | Rationale |
|-----------|---------|-----------|
| Review contains **demonstrably false** factual claim about your paper | Rebuttal first; AC note if reviewer doubles down | AC needs clean record |
| **Sub-standard review** (copy-paste, contradicts paper, ignores evidence) | AC-only / Author's Advocate | Not for public flame wars |
| **Score-relevant context** AC must know but reviewers shouldn't debate | AC-only | e.g. emergency rebuttal constraint, track mismatch |
| **Clarify process** (wrong review assigned, duplicate review) | Official Comment to AC/PC | Factual, brief |
| **Mediation request** (ACM MM Author's Advocate) | Email + optional AC note | Independent of TPC |

## When NOT to use

- ❌ Second rebuttal smuggled through AC channel (ICML explicitly warns against this)
- ❌ Attacking reviewer competence in public Official Comment
- ❌ New experiments or major new claims **only** in AC note (put evidence in main rebuttal)
- ❌ Every minor disagreement — exhaust public rebuttal first

## Decision flow

```text
Issue flagged (bad faith / factual error / AC-only context)
  → Can it be resolved in Author Rebuttal with evidence? → YES → rebuttal only
  → NO or also needs AC awareness?
       → Venue allows AC-only? → YES → draft OFFICIAL_COMMENT draft
       → Only Author's Advocate? → email template + log in brief
       → No channel? → rebuttal + factual tone; note limitation in strategy summary
```

Strategy link: `Escalate to AC` posture in [strategy-decision.md](../strategy-decision.md).

## Draft structure (AC-only / restricted Official Comment)

Keep **≤300 words** unless venue specifies otherwise. Factual, neutral, numbered.

```text
Dear Area Chair,

We thank the reviewers for their time. We have addressed all substantive points in our
author rebuttal. We write this confidential note only regarding [one specific issue].

1. Factual discrepancy: Reviewer {ID} states "{quote}". In our submission, {Table/Fig/§}
   shows {fact}. We have clarified this in rebuttal point {anchor}.

2. Request: We ask that the meta-review consider {specific ask — e.g. that this concern
   was based on a misread of Table 2}.

We remain happy to clarify further within policy.

Thank you,
Authors
```

## Draft structure (public Official Comment — rare for authors)

Use when venue expects authors to post under "Official Comment" instead of a separate Rebuttal invitation (uncommon — verify first):

- Same evidence standards as rebuttal
- Same anonymity rules
- Shorter; point to rebuttal sections by anchor ID

## ACM MM specific

- Primary artifact: **Rebuttal** button, one per review ([ACM MM author pages](https://acmmm2025.org/information-for-authors/)).
- **No external links** in rebuttal; self-contained text.
- **Author's Advocate**: for demonstrably sub-standard reviews or entirely false statements — independent mediation; document in brief before contacting.
- Reviewers instructed **not to weigh new experiments** from rebuttal — do not rely on AC note to introduce new results.

## ICCV / CVPR family

- Optional **confidential comment to AC** (check year Author Guidelines).
- One-page PDF rebuttal remains the main vehicle; AC note is for review-quality issues only.

## ICML family

- Per-review 5000-char responses are primary.
- **Confidential comments to AC exist** but must **not** be used as a late rebuttal channel.
- Reader-restricted notes via OpenReview — confirm 2025 vs 2026 wording in brief.

## Safety gates (additional)

- [ ] AC note does not repeat entire rebuttal — points to anchors
- [ ] No ad hominem; quote review verbatim for factual disputes
- [ ] Readers set correctly (AC/SAC/PC only when confidential)
- [ ] User approved send (`user_confirmed_official_comment`)
- [ ] Author's Advocate email fact-checked against submission

## Output files

```text
OFFICIAL_COMMENT_AC.md          # paste-ready restricted note
OFFICIAL_COMMENT_PUBLIC.md      # if venue uses public Official Comment for authors
AUTHORS_ADVOCATE_EMAIL.md       # ACM MM-style mediation (optional)
```

Include in standard package when drafted — see [qa-checklist.md](../qa-checklist.md).

## QA additions

- [ ] Main rebuttal already covers science; AC note adds **meta** context only
- [ ] Tone suitable if forwarded to reviewer (assume leaks)
- [ ] Escalation proportionate — not every weak review warrants AC contact
