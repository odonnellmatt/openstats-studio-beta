# OpenStats Studio Beta — version history

Current release: **[Beta 0.1.3](https://github.com/odonnellmatt/openstats-studio-beta/releases/tag/v0.1.3-beta.1)**
· [Downloads](README.md#download-beta-013)

Earlier beta releases have been removed from the Releases page so that only the
current, corrected build is downloadable. Their contents are recorded here.

---

## Beta 0.1.3 — 20 July 2026

**Statistical correctness release.** All 145 analysis procedures were verified
against independent references — published critical-value tables, textbook
worked examples and independent libraries (SciPy, statsmodels, scikit-learn,
linearmodels, arch) — rather than against the application's own code. Ten
defects were found and fixed.

**Anyone who used the affected procedures in an earlier beta should re-run those
analyses.**

### Corrected results

- **Grubbs' outlier test** used a conversion that was not the inversion of its
  published definition and reported a "significant outlier" on essentially any
  dataset, including clean ones. It now reproduces the published critical values
  exactly. Previously flagged outliers were frequently artefacts.
- **ADF / KPSS unit-root tests** were locked to "constant only" with no trend
  option, so a series stationary around a trend was reported as non-stationary
  and differencing was advised. A **Deterministic terms** option was added, and
  running constant-only on an obviously trending series now warns.
- **Repeated-measures sphericity (Mauchly's W, Greenhouse–Geisser ε)** used a
  non-orthonormal contrast and reported violations on data satisfying the
  assumption exactly. F, p and effect sizes were never affected.
- **ARIMA forecasting** of a differenced series (d ≥ 1) had no drift term, so a
  trending series forecast a flat line and scored worse than assuming no change.
  A **Trend / drift** option was added, drift is included by default once
  differenced, and backtests now display naive baselines.
- **Mardia's multivariate normality test** used the wrong covariance divisor,
  making it overly conservative in small samples.
- **Robust multivariate outlier screening** now uses a Minimum Covariance
  Determinant fit; its false-alarm rate previously rose with the correlation
  between variables.
- **Goodness-of-fit** silently produced an infinite chi-square and p = 0 when a
  category was missing or mistyped in expected proportions; it now explains the
  problem.

### Corrected reporting

- **Distance correlation** gained a permutation p-value and now discloses that
  the statistic is biased away from zero in small samples.
- **Descriptives** report `none` for the mode of an all-distinct variable rather
  than silently printing the minimum.
- Mixed models label AIC/BIC `n/a (REML)` where undefined; a duplicate
  probability column was removed from Bayesian output; robust regression column
  headings were aligned with the other regression tables.

### Safety

- **Mistyped analysis options are refused rather than silently ignored.**
  Previously an unrecognised setting was dropped and the analysis ran with its
  default, which could reverse a conclusion without warning. This also protects
  saved projects and exported reproducibility scripts from a renamed option
  quietly changing what is run.

### Verification

All 145 procedures are covered by independent numerical verification; the engine
test suite now stands at 1,394 tests. Kaplan–Meier and the log-rank test
reproduce the Freireich 6-MP trial exactly (χ² = 16.79, p = 4.17 × 10⁻⁵), and Cox
regression matches a from-definition Efron partial-likelihood implementation to
six decimal places.

**Platforms:** macOS 13+ (Apple Silicon), Windows 10/11 x64, Windows 11 ARM64.

---

## Beta 0.1.2 — 16 July 2026

- **Standard regression output**: the results page opens with the coefficient
  table and combined fit statistics (R², adjusted R², F, information criteria,
  Durbin–Watson), followed by the estimated equation and the ANOVA table — the
  familiar EViews/SPSS/R presentation.
- **Self-explanatory diagnostics**: every diagnostic test carries a
  plain-language **Note** column stating what the result means at the chosen
  significance level, with consistent significance stars on every p-value column.
  The Note column can be shown or hidden from **Table style**, and footnotes are
  numbered.
- **Better tables**: tables size to their content rather than stretching across
  the page, stay centred while being resized, and use consistent typography with
  more comfortable column spacing.
- **Exports that match the screen**: Word, PDF, HTML and Markdown exports follow
  the on-screen section order and include diagnostic charts (coefficient
  intervals, residuals vs fitted, Q–Q plot).
- **Mapping, graphing and charting**: independent map layers with per-layer
  sources and styling, cancellable rendering for large graphs, and a reworked
  Chart Studio ribbon with a Selection Pane supporting keyboard selection,
  lock/reorder/inspect actions and undo/redo.
- **Guidance everywhere**: concise working help for every option across the
  analysis catalogue.

**Platforms:** macOS 13+ (Apple Silicon), Windows 10/11 x64, Windows 11 ARM64.

---

## Beta 0.1.1 — 15 July 2026

- **Windows support**: first native installers for Windows x64 and Windows on
  ARM. On ARM devices the application runs natively while the bundled analytics
  engine uses Windows' built-in x64 compatibility layer.
- **Results tables**: every column — including the last — can be resized, and
  adjusted widths persist across navigation, autosave and project save/reopen.
  Table selection clears correctly and spacing improved.
- **Save, copy and export**: image save/copy failures fixed; "Export selected" to
  Word produces a genuine `.docx` document rather than a ZIP archive, alongside
  HTML, PDF and Markdown exports.
- **Equations**: estimated equations render as clean, unboxed mathematical text,
  consistently in the main window and the results pop-out.
- **Method help**: every option in every analysis dialog provides working,
  keyboard-accessible help.
- **Graph Studio**: running analyses can be cancelled, and very large graphs
  warn or are safely blocked instead of freezing the application.
- **Performance and packaging**: smaller application bundle and faster start-up.

**Platforms:** macOS 13+ (Apple Silicon), Windows 10/11 x64, Windows 11 ARM64.

---

## Beta 0.1.0 build 2 — 14 July 2026

- Bayesian estimation engine (conjugate foundation plus MCMC sampling).
- Machine-learning workbenches: classification, regression, clustering and
  anomaly detection.
- Network analysis procedures.
- Graph Studio: new graph document model and canvas screen.
- Expanded chart capability detection and data export.
- Native map document model and analysis menu updates.

**Platform:** macOS 13+ (Apple Silicon).

---

## Beta 0.1.0 — 13 July 2026

First public evaluation build, for macOS Apple Silicon. Brought data
preparation, statistical analysis, structured results, charts, maps and export
workflows into one local desktop application. Released to evaluate installation,
usability, compatibility and real-world research workflows ahead of a wider
release.

**Platform:** macOS 13+ (Apple Silicon).
