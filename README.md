# Omnirebuttal

**Unified Cursor Agent Skill for peer-review author responses** — CV one-page PDF, OpenReview threads, ICML character limits, journal point-by-point letters, and ARR/TMLR rolling revision.

Router + shared kernel + specialized artifact branches. Not a lowest-common-denominator merge.

## Install

### Cursor (recommended)

Clone into your personal skills directory:

```bash
git clone https://github.com/Iayce/omnirebuttal.git ~/.cursor/skills/omnirebuttal
```

Or symlink:

```bash
ln -s /path/to/omnirebuttal ~/.cursor/skills/omnirebuttal
```

Cursor loads `SKILL.md` automatically when the agent detects rebuttal-related tasks.

### Claude Code / other agents

Copy the repository root (contains `SKILL.md`) into your agent's skills folder and follow that platform's skill discovery rules.

## When it triggers

- Conference rebuttal (CVPR/ICCV/ECCV 1-page PDF, NeurIPS/ICLR/ACM MM OpenReview, ICML per-review text)
- Journal major/minor revision response letters
- ARR / TMLR rolling responses
- Strategy-only: Issue Board, triage, `REVISION_PLAN`

Keywords: `rebuttal`, `author response`, `审稿回复`, `逐点回复`, `修回信`, `OpenReview response`.

## Workflow (9 steps)

| Step | Module |
|------|--------|
| 0 | **Venue research** — official rules + community tips → `VENUE_BRIEF.md` |
| 1 | Intake & route by artifact family |
| 2 | Triage → Issue Board |
| 3 | Strategy (champion, color-code, AC escalation) |
| 4 | **Experiment plan** — run / clarify / defer when reviewers ask for numbers → `EXPERIMENT_PLAN.md` |
| 5 | Draft (venue-specific artifact + optional Official Comment) |
| 6 | Compress & fit (page-fill for 1-page PDF; char budget) |
| 7 | **Citation verify** — LightRead CLI (`lr`) when references flagged |
| 8 | **Coverage audit** — reviewer × concern × response map |
| 9 | Safety gates + QA |

See [CHANGELOG.md](CHANGELOG.md) for version history.

Start at [`SKILL.md`](SKILL.md).

## Artifact families

| Family | Venues (examples) | Output |
|--------|-------------------|--------|
| `ONE_PAGE_PDF` | CVPR, ICCV, ECCV | 1-page `rebuttal.tex` |
| `PER_REVIEW_TEXT` | ICML, KDD | Text per reviewer + char limit |
| `THREADED_DISCUSSION` | NeurIPS, ICLR, ACM MM | OpenReview thread(s) |
| `JOURNAL_POINT_BY_POINT` | Nature, R&R journals | Response letter + change map |
| `ROLLING_REVISION` | ARR, TMLR | Response + revision plan |

## Tools

```bash
scripts/count_limits.sh draft.txt --chars --limit 5000

# Citation verification (optional; requires lightread-cli)
lr auth status --verify --format json
lr web fetch "https://aclanthology.org/2024.findings-acl.300/" --format json
```

Related: [references/citation-verification-lightread.md](references/citation-verification-lightread.md)

## Repository layout

```text
SKILL.md                 # Agent entry point
references/              # Kernel + artifact guides + compression
scripts/count_limits.sh  # Character/word limit helper
```

## Provenance

Distilled from public rebuttal guides (Devi Parikh, Zeller, Grosser, Merrie, CVPR author kit, etc.), OpenReview documentation, venue author pages, and open-source rebuttal skills on SKMP/GitHub. See [`references/external-sources.md`](references/external-sources.md).

## License

MIT — see [LICENSE](LICENSE).

## 中文简介

Omnirebuttal 是一个面向 Cursor / Agent 的统一 **rebuttal（作者回复）** Skill：自动按会议/期刊形态路由（CV 一页 PDF、OpenReview 线程、ICML 字数限制、期刊逐点修回信等），并在每次回复前强制调研当届 venue 官方规则与社区经验；对审稿人提出的**补实验需求**提供分级决策（跑 / 重分析 / 澄清 / 延期），必要时起草 Official Comment / AC 私密说明。

安装：`git clone` 到 `~/.cursor/skills/omnirebuttal` 即可。
