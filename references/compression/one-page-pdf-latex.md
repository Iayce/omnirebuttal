# One-Page PDF LaTeX (CVPR / ICCV / ECCV)

Official constraints from CVPR author-kit `rebuttal.tex`. **No external links.** Anonymity required.

## Hard rules

- **1 page maximum** including references and figures; overlength = not reviewed
- Two-column, 10pt Times, single-spaced
- Do not alter margins/fonts to cheat length
- Figures optional but must be print-legible without zoom
- Figure captions 9pt; `\includegraphics[width=0.8\linewidth]{...}` typical
- Reset `\setcounter{figure}{N}` / `{table}` so rebuttal numbering ≠ main paper

## Layout tactics

### 1. Principal Arguments block (Grosser)

Use 3–5 `\paragraph{Argument title.}` or bold headings with **conclusion-first titles**:

```latex
\paragraph{Under a matched L0 budget, our method achieves higher ASR than adapted PGD/CW (@R1, @R3).}
\begin{itemize}\setlength\itemsep{0pt}
  \item Shared setting: 196 modified pixels on ImageNet; see Table~\ref{tab:rebuttal-baseline}.
  \item ...
\end{itemize}
```

### 2. @All shared evidence (playbook / FastJSMA)

One home for merged concerns — `table*` or compact single-column table:

```latex
\begin{table}[t]
\centering
\small
\begin{tabular}{lccc}
\toprule
Method & ASR (\%) & L2 & Time (ms) \\
\midrule
PGD-196px & ... & ... & ... \\
CW-196px-extrema & ... & ... & ... \\
Ours & ... & ... & ... \\
\bottomrule
\end{tabular}
\caption{@All: Baselines under unified 196-pixel budget (ImageNet).}
\label{tab:rebuttal-baseline}
\end{table}
```

Per-reviewer text: "See Table~\ref{tab:rebuttal-baseline} (@All)."

### 3. Minimal tables

- Use `booktabs`, `\small` or `\footnotesize`
- Columns: Method | key metric(s) | Time — drop SE, extra datasets, ablation columns
- Abbreviate method names consistently

### 4. Table → figure

When rows > 6 or methods > 5 with 2+ metrics: grouped bar chart at `width=\linewidth` or `0.9\linewidth`.
Dual-axis only if Time vs ASR story is decision-critical (keep readable at print size).

### 5. Minipage side-by-side

```latex
\noindent\begin{minipage}[t]{0.55\linewidth}
% table or small figure
\end{minipage}\hfill
\begin{minipage}[t]{0.42\linewidth}
\small
\textbf{Takeaway.} Under matched budget, ours wins on ASR; PGD is faster but lower ASR.
\end{minipage}
```

No blank line between minipages (causes column break).

### 6. Formula compression

One-line gradient or loss identity instead of paragraph (virtual-label / heuristic defense).

### 7. Opener compression

≤4 sentences: thanks + 2 strengths with (@Rx) + roadmap sentence.

## Trim order when over 1 page

1. Remove duplicate per-reviewer tables → point to @All
2. Batch all minor presentation fixes in one sentence
3. Shorten orange-tier prose; keep bullets
4. Reduce opener/closing
5. Shrink figure margins slightly (not below readable)
6. **Never** delete critical table/figure or reproducibility explanation first

## Print check

- Font in figures ≥ 6pt (ECCV guidance)
- Line widths visible in print
- Assume reviewer prints; no "zoom to see"

## CVPR policy reminder

- Reviewers discouraged from requiring huge new experiments for rebuttal
- Do not add unrequested major new contributions
- Requested clarifications + fairly scoped new numbers OK when reviewer asked

See [visual-density-patterns.md](visual-density-patterns.md) and case [../cases/fastjsma-iccv2025.md](../cases/fastjsma-iccv2025.md).
