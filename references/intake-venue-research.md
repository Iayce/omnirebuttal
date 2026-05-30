# Venue Research (Mandatory Intake)

**Every rebuttal session starts here.** Do not triage or draft until this step completes or the user explicitly skips with written acknowledgment.

Goal: bind the session to **this venue + this year + this track** — not a stale row in `venue-matrix.md` or memory from a prior conference.

## When to run

| Trigger | Action |
|---------|--------|
| New rebuttal task | Full research → `VENUE_BRIEF.md` |
| User names venue/year only | Research first, then ask for reviews |
| Follow-up round same venue | Delta research (deadline, new limits, discussion rules) |
| User says "skip research" | Log `venue_research: skipped_by_user` in brief |

## Tooling (web-access)

All live lookups go through the **web-access** skill (or Cursor `WebSearch` / `WebFetch` / browser MCP when web-access CDP is unavailable).

Search philosophy: **official first, community second, cross-check third.**

| Priority | Source type | Examples |
|----------|-------------|----------|
| P0 | Official venue site | Author guidelines, CFP, rebuttal instructions, LLM policy |
| P0 | OpenReview / CMT docs | Rebuttal stage, default forms, character limits for **this** venue ID |
| P1 | Conference blog / PC posts | ICLR blog, NeurIPS FAQ, ICML author instructions |
| P2 | Community experience | 小红书, 知乎, Reddit r/MachineLearning, Twitter/X, 一亩三分地, 博客 |
| P3 | Prior year same venue | Useful for culture; **verify** against current year |

For 小红书 / 微博 / 动态站点: use browser MCP or web-access CDP — static fetch often fails.

## Research checklist

Copy into `VENUE_BRIEF.md` (template: [templates/venue-brief-template.md](templates/venue-brief-template.md)).

### A. Artifact & platform

- [ ] Artifact family (`ONE_PAGE_PDF` / `PER_REVIEW_TEXT` / `THREADED_DISCUSSION` / …)
- [ ] Platform (OpenReview, CMT, email to editor, …)
- [ ] Rebuttal UI label ("Rebuttal", "Author Response", "Official Comment", …)

### B. Hard limits

- [ ] Page / character / word cap (per paper vs per review vs per post)
- [ ] Figure/table allowed in text rebuttal?
- [ ] Revised PDF upload allowed? When?
- [ ] External links allowed?

### C. Policy gates

- [ ] Anonymity rules (URLs, self-citation phrasing, code links)
- [ ] New experiments / new results in rebuttal?
- [ ] LLM / AI assistance disclosure required?
- [ ] **Official Comment** or **confidential AC channel** available? Limits?

### D. Process & timing

- [ ] Rebuttal window (start/end, timezone)
- [ ] Single-shot vs multi-round discussion
- [ ] Reviewer obligation to read/respond (if stated)

### E. Venue-specific escalation paths

- [ ] Author's Advocate / Ombuds / mediation email (e.g. ACM MM)
- [ ] PC contact for policy disputes
- [ ] Journal editor vs AE routing

### F. Community intel (labeled `community`, not official)

- [ ] 3–5 actionable tips from recent cycles (space tricks, AC reading habits, common reject reasons)
- [ ] Known pitfalls ("reviewers ignore revised PDF", "don't use Official Comment for …")
- [ ] Link each tip to source URL or platform post

## Search query patterns

Replace `{VENUE}` `{YEAR}` `{TRACK}`:

```text
{VENUE} {YEAR} author rebuttal guidelines
{VENUE} {YEAR} OpenReview author response character limit
site:openreview.net {VENUE} {YEAR} rebuttal
{VENUE} rebuttal 经验 site:xiaohongshu.com
{VENUE} rebuttal 知乎 {YEAR}
{VENUE} author response reddit {YEAR}
ICCV confidential comment area chair  (when family = ONE_PAGE_PDF)
ICML AC-only comment OpenReview
```

## Outputs

1. **`VENUE_BRIEF.md`** in project rebuttal folder (e.g. `ACMMM/rebuttal/VENUE_BRIEF.md`) — session source of truth.
2. **Route confirmation** — update artifact family in intake if research contradicts guess.
3. **Matrix patch** — if official rules differ from [venue-matrix.md](venue-matrix.md), append dated note in brief and optionally patch matrix row.

## Conflict resolution

| Situation | Rule |
|-----------|------|
| Official vs community conflict | Official wins |
| Two official pages conflict | Prefer Author Instructions > Reviewer Guidelines > old blog post; note ambiguity in brief |
| Limit not published | Assume most conservative limit for family; flag `AUTHOR_INPUT_NEEDED` |
| OpenReview form differs from website | **OpenReview form wins** for submission |

## Gate: proceed to Triage?

Proceed only when:

- `VENUE_BRIEF.md` exists with P0 fields filled, **or**
- User explicitly waives research (logged in brief).

Missing P0 → stop and report what could not be verified.

## Integration with Official Comment

During research, explicitly record:

- Whether authors may post **Official Comment** (OpenReview) vs only **Author Rebuttal**
- Whether **AC-only / SAC+PC-only** readers exist
- Venue prohibition on using confidential channels as "second rebuttal"

Then load [artifacts/official-comment.md](artifacts/official-comment.md) if any escalation or AC-facing note is plausible.
