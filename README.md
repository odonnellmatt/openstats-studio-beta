# OpenStats Studio Beta 0.1.1

## Downloads

### **[⬇ Download for macOS Apple Silicon](https://github.com/odonnellmatt/openstats-studio-beta/releases/download/v0.1.1-beta.1/OpenStats-Studio-Beta-0.1.1-macOS-Apple-Silicon.dmg)**

**macOS 13 or later · Apple Silicon · 285 MB DMG**

### **[⬇ Download for Windows x64](https://github.com/odonnellmatt/openstats-studio-beta/releases/download/v0.1.1-beta.1/OpenStats-Studio-Beta-0.1.1-Windows-x64-setup.exe)**

**Windows 10/11 · x64 · 217 MB installer**

### **[⬇ Download for Windows on ARM](https://github.com/odonnellmatt/openstats-studio-beta/releases/download/v0.1.1-beta.1/OpenStats-Studio-Beta-0.1.1-Windows-ARM64-setup.exe)**

**Windows 11 · ARM64 · 216 MB installer**

This is prerelease beta software. Please read the beta notice below before use.

OpenStats Studio is a local-first desktop statistics application for people who
want to move from data to clear, structured results in one workspace.

It is designed for researchers, students, analysts and educators who need a
practical environment for preparing data, running statistical analyses,
reviewing results and producing useful outputs without sending their datasets
to a hosted analysis service.

## What you can explore

- Import, inspect and prepare common research datasets.
- Run a broad collection of statistical and econometric analyses, including
  Bayesian, machine-learning and network-analysis workbenches.
- Review structured output, diagnostics and supporting guidance.
- Organise results and reopen saved projects.
- Create charts, graphs, maps and report-ready exports.
- Work locally by default. Optional online map layers are clearly identified.

The beta is intentionally being released for hands-on evaluation. Try it with
realistic but non-critical projects and let us know what works well, what feels
unclear and where the workflow can improve.

## What's new in Beta 0.1.1

- First Windows builds: x64 and Windows on ARM installers join the macOS DMG.
- Results tables: every column (including the last) can be resized, and your
  column widths now persist across navigation and project save/reopen.
- Reliable save, copy and export of results — image copy/save failures are
  fixed, and Word export now produces a genuine `.docx` file.
- Cleaner presentation of estimated equations and improved table readability.
- Every option in every analysis dialog now has working help.
- Graph Studio: analyses can be cancelled, and very large graphs warn or are
  safely blocked instead of freezing the application.
- Faster loading through smaller application bundles.

## Download

The direct download buttons at the top of this page download the current beta
for each platform. Release notes and checksum files are also available from
**Releases**:

**[View OpenStats Studio Beta 0.1.1 release details](https://github.com/odonnellmatt/openstats-studio-beta/releases/tag/v0.1.1-beta.1)**

Current beta platforms:

- macOS 13 or later on Apple Silicon (`arm64`). Intel Macs are not supported
  by this build.
- Windows 10/11 on x64.
- Windows 11 on ARM (`arm64`). The bundled analytics engine currently runs
  through Windows' built-in x64 compatibility layer; a fully native engine is
  planned.

## Important beta notice

This is prerelease software provided for evaluation and testing. Features,
project formats and outputs may change, and defects may still be present.

- Do not rely on the beta as the sole copy of important work.
- Keep backups of source data and saved projects.
- Independently review statistical specifications and important conclusions.
- Do not use it as the only basis for safety-critical, clinical, legal or
  financial decisions.
- There is currently no automatic update channel.

The macOS beta is locally signed for integrity but is not yet Apple-notarised,
so macOS may display an unidentified-developer warning. The Windows installers
are not yet code-signed, so Microsoft Defender SmartScreen may display a
"Windows protected your PC" warning. In both cases, confirm that the downloaded
file has the published SHA-256 before proceeding. Do not bypass the warning if
the checksum differs.

## Install on macOS

1. Download the `.dmg` from the latest beta release.
2. Confirm its SHA-256 against the value published with the release.
3. Open the disk image and drag **OpenStats Studio** into **Applications**.
4. Launch the application. If macOS shows an unidentified-developer warning,
   choose **Open Anyway** in **System Settings → Privacy & Security** only
   after the checksum matches.
5. The first launch may take a little longer while the bundled local analytics
   engine starts.

## Install on Windows

1. Download the installer that matches your machine: `x64` for ordinary
   Intel/AMD PCs, `ARM64` for Windows-on-ARM devices such as Snapdragon
   laptops. (**Settings → System → About → System type** shows which you have.)
2. Confirm its SHA-256 against the value published with the release
   (`certutil -hashfile <file> SHA256` in a terminal).
3. Run the installer. If SmartScreen appears, choose **More info → Run anyway**
   only after the checksum matches.
4. Launch **OpenStats Studio** from the Start menu. The first launch may take a
   little longer while the bundled local analytics engine starts.

No separate Python, R, Node.js or internet connection is required for ordinary
analysis. Selecting an online map provider can contact that provider and reveal
the geographic area being viewed; bundled and user-supplied map data can be used
offline.

## Feedback

Please use this repository's **Issues** section for beta feedback. Include:

- your operating system version and device model
- the action you were attempting
- what you expected and what happened
- reproducible steps using non-confidential data

Do not attach confidential datasets, personal information or private project
files to a public issue.

## Source and intellectual property

This repository is a download and beta-feedback page only. It does not contain
the OpenStats Studio application source code.

## Screenshots of 0.1.1

### Data view
<img width="1794" height="1128" alt="Screenshot 2026-07-15 at 3 18 38 pm" src="https://github.com/user-attachments/assets/6654eb2a-5c60-4488-ac33-a532e2039185" />

### Some methods
<img width="1796" height="1125" alt="Screenshot 2026-07-15 at 3 18 54 pm" src="https://github.com/user-attachments/assets/be1b73c1-1f96-495c-9540-e3cba980ff96" />

### Example method (MLR)
<img width="1795" height="1125" alt="Screenshot 2026-07-15 at 3 19 24 pm" src="https://github.com/user-attachments/assets/bb01e934-64da-4714-9148-1778cd60584d" />

### Example output
<img width="1795" height="1126" alt="Screenshot 2026-07-15 at 3 19 55 pm" src="https://github.com/user-attachments/assets/f3b5ee86-3f71-4935-ae86-1e4f2aa5c341" />

### Chart gallery
<img width="1794" height="1124" alt="Screenshot 2026-07-15 at 3 20 20 pm" src="https://github.com/user-attachments/assets/d0a17ba2-bedf-48ed-bb73-982325fe9653" />


