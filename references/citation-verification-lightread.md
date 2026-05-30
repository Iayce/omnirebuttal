# Citation Verification (LightRead CLI)

Run when a reviewer flags **citation errors**, **hallucinated references**, or when the rebuttal commits to **correcting BibTeX** in camera-ready. Prefer **LightRead CLI (`lr`)** over ad-hoc web search — it returns structured, citable metadata.

**Skill dependency:** `lightread-cli` (global install: `bun add -g lightread-cli` or `npm i -g lightread-cli`).

## When to run

- Reviewer says author list / venue / title is wrong (e.g. MemeMQA, MMBench).
- Rebuttal text names corrected authors — verify before submit.
- Manuscript `references.bib` updated during rebuttal prep — spot-check changed keys only.
- User asks to "用 LightRead / Literead 检查引用".

## Agent workflow

1. **Auth check** (once per session if unsure):
   ```bash
   lr auth status --verify --format json
   ```
2. **Locate** flagged keys in manuscript `.bib` and in-text `\cite{...}`.
3. **Resolve** each paper (prefer official page over arXiv-only when venue matters):

   ```bash
   # arXiv / general discovery
   lr search "Exact Paper Title" --format json

   # Official proceedings page (ACL Anthology, etc.)
   lr web fetch "https://aclanthology.org/2024.findings-acl.300/" --format json

   # arXiv metadata page
   lr web fetch "https://arxiv.org/abs/2307.06281" --format json

   # ECCV / Springer / DBLP when proceedings page is blocked
   lr websearch "Paper Title ECCV 2024 pages 216 233" --format json
   ```

4. **Compare** against local BibTeX: `author`, `title`, `booktitle`/`journal`, `year`, `pages`, `doi`, `url`.
5. **Fix** `.bib` in working manuscript; mention fix in rebuttal with **exact author list + venue** (shows seriousness).
6. **Do not** invent DOI/pages — if unresolved, mark `AUTHOR_INPUT_NEEDED` and use conservative arXiv entry until confirmed.

## Command notes (v0.3.x)

| Goal | Command | Notes |
|------|---------|-------|
| Search papers | `lr search "<query>" --format json` | Combines arXiv + Scholar; Scholar may warn if API key stale — arXiv still works |
| Fetch page → markdown/json | `lr web fetch <url> --format json` | ACL Anthology often embeds official `@inproceedings{...}` block |
| Web / DBLP discovery | `lr websearch "<query>" --format json` | Good for ECCV LNCS volume + page range |
| BibTeX export | `lr search ... --format bibtex` | Optional; cross-check against official page |

**Not available in all CLI builds:** legacy docs mention `lr read <url>` — use `lr web fetch` instead.

## Rebuttal phrasing (after verification)

> We will correct the [Paper] citation (R4): [Paper] should cite [Author1, Author2, …] ([Venue Year]). We have already updated the BibTeX entries in our working manuscript.

Only claim "already updated" if the `.bib` file was actually edited in this session.

## QA linkage

- [qa-checklist.md](qa-checklist.md) — Citation verification block
- [safety-gates.md](safety-gates.md) — no invented references
- [external-sources.md](external-sources.md) — LightRead row

## Example (MemeSleuth-Bench / ACM MM 2026)

| Key | Issue | Verified via | Fix |
|-----|-------|--------------|-----|
| MemeMQA | Wrong authors/venue | `lr web fetch` ACL Anthology | Agarwal, Sharma, Nakov, Chakraborty — Findings ACL 2024, pp. 5042–5078 |
| MMBench | Wrong author list | `lr web fetch` arXiv + `lr websearch` DBLP/ECCV | Liu, Duan, Zhang, … — ECCV 2024, LNCS 15064, pp. 216–233 |
