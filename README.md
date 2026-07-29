# OpenStats Studio — Public Beta

A local-first desktop statistics application. Prepare data, run analyses, review
structured results and produce report-ready output in one workspace — on your own
machine, without sending datasets to a hosted service.

Built for researchers, students, analysts and educators.

---

## Download Beta 0.1.4

| Platform | Requirements | Download |
| --- | --- | --- |
| **macOS** | macOS 13+ · Apple Silicon | **[⬇ Download DMG](https://github.com/odonnellmatt/openstats-studio-beta/releases/download/v0.1.4-beta.1/OpenStats-Studio-Beta-0.1.4-macOS-Apple-Silicon.dmg)** · 240.2 MiB |
| **Windows** | Windows 10/11 · x64 | **[⬇ Download installer](https://github.com/odonnellmatt/openstats-studio-beta/releases/download/v0.1.4-beta.1/OpenStats-Studio-Beta-0.1.4-Windows-x64-setup.exe)** · 196.2 MiB |
| **Windows on ARM** | Windows 11 · ARM64 | **[⬇ Download installer](https://github.com/odonnellmatt/openstats-studio-beta/releases/download/v0.1.4-beta.1/OpenStats-Studio-Beta-0.1.4-Windows-ARM64-setup.exe)** · 195.9 MiB |

Not sure which Windows build? **Settings → System → About → System type.**

<!-- Download links intentionally pin the release tag. GitHub's
     /releases/latest/ endpoint ignores prereleases, so a /latest/download/
     URL 404s while every release here is a prerelease. Update the tag in
     these three links when publishing a new beta. -->

[Release notes and checksums](https://github.com/odonnellmatt/openstats-studio-beta/releases/tag/v0.1.4-beta.1)
 · [All releases](https://github.com/odonnellmatt/openstats-studio-beta/releases)
 · [Version history](RELEASE_NOTES.md)

> **Prerelease software.** Please read the [beta notice](#beta-notice) before use.

---

## What's in Beta 0.1.4

### New: qualitative and mixed-methods research

A full qualitative surface alongside the statistics: a **coding workspace**,
codebook manager, cases, memos, queries, matrices, code flow and code network
views, quote wall, words studio and a qualitative report builder — plus a
**mixed-methods bridge** with Creswell design templates and a guided sample-study
walkthrough.

### New: methodology transparency

Method cards and citations, generated methods paragraphs, Detailed Mode guidance
throughout, latent variable models (**CFA and SEM**), agreement measures, text and
content analysis, QCA and Q-methodology. The **study record** locks an analysis
plan with a SHA-256 hash and classifies every subsequent run as *pre-specified* or
*exploratory*, so the distinction is recorded rather than remembered.

### Reworked method setup

The Model panel is now two independently scrolling sections divided by a
draggable, keyboard-operable splitter. Adding a variable no longer pushes the
variable browser down the page — building a model with fifteen predictors no
longer means scrolling back to the list after every click. Where a method's roles
can never grow, the panel sizes itself to its content instead of reserving space.

### Correctness and reachability fixes

**If you used any of these in an earlier beta, please re-run that analysis.**

- **One column can no longer fill two roles in a single analysis.** 32 procedures
  either crashed inside pandas or silently de-duplicated and fitted a model that
  was never requested — including independent-samples t-test, one-way ANOVA,
  Mann–Whitney, Kruskal–Wallis and Tukey HSD. Now refused centrally with a clear
  message.
- **Survey weights** can no longer double as an analysis, grouping or axis
  variable in weighted descriptives and crosstabs.
- **An entire Text & Content Analysis submenu (11 procedures)**, plus the
  agreement, CFA, SEM and GLMM entries, were unreachable from the macOS menu bar.
  The menu is regenerated and a test now prevents a declared group being left
  unattached.
- A **cold validation review of seven procedures** was carried out independently
  of the code that implements them, and every finding closed.

### Earlier: Findings Builder (0.1.3)

A structured notebook inside your project, built from the results you actually
ran. Send any table, chart, graph, coefficient plot or interpretation into it
straight from Results, write headings, key findings and notes around them, and
export the finished document to **Word, PDF, HTML or Markdown**.

Blocks can stay **live** — refreshed from the analysis they came from when you
re-run it — or be **frozen as a snapshot** so a figure you have already written
about cannot move under you. Each block records the run, method, dataset,
variables and execution time it came from.

[More detail below](#findings-builder).

Full detail is in **[RELEASE_NOTES.md](RELEASE_NOTES.md)**.

### Earlier betas

| Version | Highlights |
| --- | --- |
| **0.1.3** | Findings Builder; all 145 procedures verified against independent references (published critical-value tables, textbook examples, SciPy/statsmodels/scikit-learn/linearmodels/arch), correcting Grubbs, ADF/KPSS, ARIMA drift, sphericity, Mardia and more; mistyped options refused rather than silently ignored |
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
- **Assemble a Findings notebook** — send any table, chart, graph, coefficient
  plot or interpretation straight from Results into a structured document, add
  headings, key findings, callouts, equations and notes around them, reorder by
  drag or keyboard, and export the whole thing to Word, PDF, HTML or Markdown.
  See [Findings Builder](#findings-builder) below.
- Build charts, graphs and maps; export to Word, PDF, HTML, Markdown and Excel.
- Save projects and reopen them with results intact.
- Work locally by default. Optional online map layers are clearly identified
  before any request is made.

---

## Findings Builder

Analysis usually ends with a pile of output and a separate document to write. The
**Findings** screen closes that gap: it is a structured notebook that lives inside
your project, built from the results you actually ran.

**Send results straight in.** From Results, Chart Studio or Graph Studio, push any
table, chart, graph, coefficient plot, diagnostic plot or generated interpretation
into the notebook — or pull in a whole session's output at once with **Import
session outputs**.

**Write around your evidence.** Add headings and sections, **Key finding**
callouts, info and warning boxes, equations, dividers and free text. Every block
can carry its own caption, comment, limitations and follow-up note, so the
caveats travel with the result instead of living in your head.

**Choose how each block tracks its source.** Blocks are *live*, *copy* or
*snapshot*. A live block follows the analysis it came from and can be refreshed
with **Update from source** when you re-run with different options; a snapshot is
deliberately frozen so a figure you have already written about cannot move under
you.

**Provenance is recorded, not reconstructed.** Each block stores the run, result,
method, dataset, variables and execution time it came from — so months later you
can still tell which analysis produced a given table.

**Keep editing without leaving.** Reorder by drag or keyboard, collapse sections,
jump back into Chart Studio or Graph Studio to adjust a figure in place, or
download any chart as PNG.

**Export the finished document** to **Word, PDF, HTML or Markdown** — all blocks
or just the ones you select. Charts embed as images, tables as real tables.

Notebooks are saved inside the project and reopen with it. The screen is fully
keyboard-navigable and has a built-in shortcuts panel.

---

## Install

**These builds are not code-signed.** The macOS app is ad-hoc signed and not
Apple-notarised; the Windows installers carry no certificate. Neither system will
open them by the normal route — each needs one deliberate extra step, set out
below. Check the SHA-256 first, and if it does not match, stop and do not
continue.

### macOS · Apple Silicon

1. **Verify the download.**

   ```bash
   shasum -a 256 ~/Downloads/OpenStats-Studio-Beta-0.1.4-macOS-Apple-Silicon.dmg
   ```

   Compare it with the [published checksum](https://github.com/odonnellmatt/openstats-studio-beta/releases/tag/v0.1.4-beta.1).
   Continue only if it matches.

2. **Install.** Open the `.dmg`, drag **OpenStats Studio** into **Applications**,
   then eject the disk image.

3. **Clear the quarantine flag.** Because the app is ad-hoc signed rather than
   issued under a developer certificate, macOS refuses it outright — typically
   *"OpenStats Studio is damaged and can't be opened"* — and on current macOS
   there is no **Open Anyway** button to fall back on. In **Terminal**:

   ```bash
   xattr -dr com.apple.quarantine "/Applications/OpenStats Studio.app"
   ```

   This removes only the marker macOS attaches to files downloaded from the
   internet. It does not modify the application.

4. **Open it.** If you saw *"cannot be opened because the developer cannot be
   verified"* instead, open **System Settings → Privacy & Security**, scroll to
   **Security**, and choose **Open Anyway**.

5. First launch takes a little longer while the bundled analytics engine starts.

### Windows · x64 and ARM64

Which installer? **Settings → System → About → System type** — *x64* for ordinary
Intel/AMD PCs, *ARM64* for Snapdragon and other Windows-on-ARM devices.

1. **Verify the download.** In Command Prompt:

   ```bat
   certutil -hashfile "%USERPROFILE%\Downloads\OpenStats-Studio-Beta-0.1.4-Windows-x64-setup.exe" SHA256
   ```

   Compare it with the published checksum. Continue only if it matches.

2. **Unblock the file.** Right-click the `.exe` → **Properties** → tick
   **Unblock** at the bottom of the **General** tab → **OK**. In PowerShell the
   equivalent is:

   ```powershell
   Unblock-File -Path "$env:USERPROFILE\Downloads\OpenStats-Studio-Beta-0.1.4-Windows-x64-setup.exe"
   ```

3. **Run the installer.** SmartScreen will show **"Windows protected your PC"**
   because the installer is unsigned. Choose **More info → Run anyway**.

4. **If Defender quarantines it,** restore it from **Windows Security → Virus &
   threat protection → Protection history** — again, only if the checksum
   matched.

5. Launch **OpenStats Studio** from the Start menu. First launch takes a little
   longer while the bundled analytics engine starts.

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

The macOS build is ad-hoc signed and **not Apple-notarised**; the Windows
installers are **not code-signed**. Both will therefore be blocked by the
operating system on first run, and clearing that block takes a deliberate manual
step — see [Install](#install). Confirm the published SHA-256 before you take it,
and do not bypass the warning if the checksum differs.

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
<img width="1796" height="1060" alt="Screenshot 2026-07-21 at 9 29 32 pm" src="https://github.com/user-attachments/assets/af546fb6-c543-4e6e-8dcb-512bc588580e" />

### Method catalogue
<img width="1796" height="1125" alt="Method catalogue" src="https://github.com/user-attachments/assets/be1b73c1-1f96-495c-9540-e3cba980ff96" />

### Configuring an analysis (multiple linear regression)
<img width="1793" height="1057" alt="Screenshot 2026-07-21 at 9 30 10 pm" src="https://github.com/user-attachments/assets/2c52406a-a09e-4619-8cb8-ff5f2b389702" />

### Results output
<img width="1795" height="1060" alt="Screenshot 2026-07-21 at 9 31 01 pm" src="https://github.com/user-attachments/assets/53f714a2-5ef5-4bed-80e6-05561ccc2435" />

### Findings Builder
<img width="1795" height="1059" alt="Screenshot 2026-07-21 at 9 35 13 pm" src="https://github.com/user-attachments/assets/a2bf2252-14c1-4a26-b812-d4d07c010212" />

### Chart gallery
<img width="1791" height="1054" alt="Screenshot 2026-07-21 at 9 31 37 pm" src="https://github.com/user-attachments/assets/1373a042-d728-44ce-9a16-fcafbd0fb1c1" />

