# OpenStats Studio — Public Beta

A local-first desktop statistics application. Prepare data, run analyses, review
structured results and produce report-ready output in one workspace — on your own
machine, without sending datasets to a hosted service.

Built for researchers, students, analysts and educators.

---

## Download Beta 0.1.3

| Platform | Requirements | Download |
| --- | --- | --- |
| **macOS** | macOS 13+ · Apple Silicon | **[⬇ Download DMG](https://github.com/odonnellmatt/openstats-studio-beta/releases/download/v0.1.3-beta.1/OpenStats-Studio-Beta-0.1.3-macOS-Apple-Silicon.dmg)** · 285 MiB |
| **Windows** | Windows 10/11 · x64 | **[⬇ Download installer](https://github.com/odonnellmatt/openstats-studio-beta/releases/download/v0.1.3-beta.1/OpenStats-Studio-Beta-0.1.3-Windows-x64-setup.exe)** · 180 MiB |
| **Windows on ARM** | Windows 11 · ARM64 | **[⬇ Download installer](https://github.com/odonnellmatt/openstats-studio-beta/releases/download/v0.1.3-beta.1/OpenStats-Studio-Beta-0.1.3-Windows-ARM64-setup.exe)** · 180 MiB |

Not sure which Windows build? **Settings → System → About → System type.**

<!-- Download links intentionally pin the release tag. GitHub's
     /releases/latest/ endpoint ignores prereleases, so a /latest/download/
     URL 404s while every release here is a prerelease. Update the tag in
     these three links when publishing a new beta. -->

[Release notes and checksums](https://github.com/odonnellmatt/openstats-studio-beta/releases/tag/v0.1.3-beta.1)
 · [All releases](https://github.com/odonnellmatt/openstats-studio-beta/releases)
 · [Version history](RELEASE_NOTES.md)

> **Prerelease software.** Please read the [beta notice](#beta-notice) before use.

---

## What's in Beta 0.1.3

**This is a statistical correctness release.** All 145 analysis procedures were
verified against independent references — published critical-value tables,
textbook worked examples and independent libraries (SciPy, statsmodels,
scikit-learn, linearmodels, arch) — rather than against the application's own
code. Ten defects were found and fixed.

**If you used any of these in an earlier beta, please re-run that analysis.**

- **Grubbs' outlier test** reported a significant outlier on almost any dataset,
  including clean ones. Now matches its published critical values exactly.
- **ADF / KPSS unit-root tests** had no trend option, so a trend-stationary
  series was called non-stationary and you were told to difference it. A
  **Deterministic terms** setting has been added.
- **ARIMA forecasts** of a differenced trending series had no drift term and came
  out flat — worse than assuming no change. A **Trend / drift** setting has been
  added and backtests now show naive baselines.
- **Sphericity (Mauchly / Greenhouse–Geisser)** reported violations on data that
  satisfied the assumption perfectly. Your F, p and effect sizes were unaffected.
- **Mardia's test**, the **robust multivariate outlier screen**, **distance
  correlation**, **goodness-of-fit** and several reporting details were corrected.
- **Mistyped analysis options are now refused rather than silently ignored** —
  previously an unrecognised setting ran the default, which could reverse a
  conclusion with no warning.

Full detail, including what changed and why, is in the
[0.1.3 release notes](https://github.com/odonnellmatt/openstats-studio-beta/releases/tag/v0.1.3-beta.1).

### Earlier betas

| Version | Highlights |
| --- | --- |
| **0.1.2** | Standard regression output (coefficients + fit statistics, equation, ANOVA); plain-language **Note** column on every diagnostic; content-sized tables; exports matching the screen; independent map layers; reworked Chart Studio ribbon |
| **0.1.1** | First Windows builds (x64 and ARM); resizable, persistent Results columns; genuine `.docx` export; cleaner equations; help in every dialog; cancellable Graph Studio |
| **0.1.0** | First public build (macOS); then Bayesian estimation and MCMC, ML workbenches, network analysis, Graph Studio and the map document model |

Full history: **[RELEASE_NOTES.md](RELEASE_NOTES.md)**

---

## What you can do with it

- Import, inspect and prepare common research datasets.
- Run 145 statistical and econometric procedures across 26 families — including
  regression and GLMs, panel and causal econometrics, time series and
  forecasting, survival, clinical and diagnostic statistics, quality and DOE,
  survey and missing-data methods, Bayesian analysis, and machine-learning and
  network workbenches.
- Review structured output with diagnostics and plain-language guidance.
- Build charts, graphs and maps; export to Word, PDF, HTML, Markdown and Excel.
- Save projects and reopen them with results intact.
- Work locally by default. Optional online map layers are clearly identified
  before any request is made.

---

## Install

### macOS

1. Download the `.dmg` above.
2. Verify its SHA-256: `shasum -a 256 <file>` — compare against the
   [published checksum](https://github.com/odonnellmatt/openstats-studio-beta/releases/tag/v0.1.3-beta.1).
3. Open the image and drag **OpenStats Studio** into **Applications**.
4. Launch it. macOS may show an unidentified-developer warning; choose **Open
   Anyway** in **System Settings → Privacy & Security** *only if the checksum
   matched*.
5. First launch takes a little longer while the bundled analytics engine starts.

### Windows

1. Download the installer matching your machine (x64 for ordinary Intel/AMD PCs,
   ARM64 for Snapdragon and similar).
2. Verify its SHA-256: `certutil -hashfile <file> SHA256`.
3. Run it. If SmartScreen appears, choose **More info → Run anyway** *only if the
   checksum matched*.
4. Launch **OpenStats Studio** from the Start menu.

No separate Python, R, Node.js or internet connection is needed for ordinary
analysis.

---

## Beta notice

This is prerelease software provided for evaluation. Features, project formats
and outputs may change, and defects may still be present.

- Do not rely on the beta as the sole copy of important work; keep backups.
- Independently review statistical specifications and important conclusions.
- Do not use it as the only basis for safety-critical, clinical, legal or
  financial decisions.
- There is no automatic update channel yet.

The macOS build is locally signed for integrity but **not yet Apple-notarised**.
The Windows installers are **not yet code-signed**. Both may therefore trigger an
operating-system warning. Confirm the published SHA-256 before proceeding, and do
not bypass the warning if the checksum differs.

---

## Feedback

Please use this repository's **[Issues](https://github.com/odonnellmatt/openstats-studio-beta/issues)**
for beta feedback. Helpful reports include:

- your operating system version and device model
- what you were trying to do
- what you expected and what actually happened
- steps to reproduce, using non-confidential data

Please do not attach confidential datasets, personal information or private
project files to a public issue.

---

## Source

This repository is a download and feedback page only; it does not contain
application source code.

---

## Screenshots

### Data view
<img width="1794" height="1128" alt="Data view" src="https://github.com/user-attachments/assets/6654eb2a-5c60-4488-ac33-a532e2039185" />

### Method catalogue
<img width="1796" height="1125" alt="Method catalogue" src="https://github.com/user-attachments/assets/be1b73c1-1f96-495c-9540-e3cba980ff96" />

### Configuring an analysis (multiple linear regression)
<img width="1795" height="1125" alt="Multiple linear regression setup" src="https://github.com/user-attachments/assets/bb01e934-64da-4714-9148-1778cd60584d" />

### Results output
<img width="1795" height="1126" alt="Results output" src="https://github.com/user-attachments/assets/f3b5ee86-3f71-4935-ae86-1e4f2aa5c341" />

### Chart gallery
<img width="1794" height="1124" alt="Chart gallery" src="https://github.com/user-attachments/assets/d0a17ba2-bedf-48ed-bb73-982325fe9653" />

*Screenshots taken in Beta 0.1.1; the interface has since been refined.*
