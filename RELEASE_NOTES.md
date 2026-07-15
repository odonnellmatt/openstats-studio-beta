# OpenStats Studio Beta 0.1.1

## **[⬇ Download for macOS Apple Silicon](https://github.com/odonnellmatt/openstats-studio-beta/releases/download/v0.1.1-beta.1/OpenStats-Studio-Beta-0.1.1-macOS-Apple-Silicon.dmg)**

**macOS 13 or later · Apple Silicon · 285 MB DMG**

## **[⬇ Download for Windows x64](https://github.com/odonnellmatt/openstats-studio-beta/releases/download/v0.1.1-beta.1/OpenStats-Studio-Beta-0.1.1-Windows-x64-setup.exe)**

**Windows 10/11 · x64 · 217 MB installer**

## **[⬇ Download for Windows on ARM](https://github.com/odonnellmatt/openstats-studio-beta/releases/download/v0.1.1-beta.1/OpenStats-Studio-Beta-0.1.1-Windows-ARM64-setup.exe)**

**Windows 11 · ARM64 · 216 MB installer**

Beta 0.1.1 is the first OpenStats Studio release available for Windows as well
as macOS, and it carries a substantial set of Results-page and reliability
fixes.

## What's new since Beta 0.1.0

- **Windows support**: native installers for Windows x64 and Windows on ARM.
  On ARM devices the application runs natively while the bundled analytics
  engine currently uses Windows' built-in x64 compatibility layer.
- **Results tables**: every column — including the last — can be resized, and
  user-adjusted column widths persist across navigation, autosave and project
  save/reopen. Table selection now clears correctly, and spacing is improved.
- **Save, copy and export**: image save/copy failures (`load failed`) are
  fixed; "Export selected" to Word now produces a genuine `.docx` document
  (no more ZIP archives), alongside direct HTML, PDF and Markdown exports.
- **Equations**: estimated equations render as clean, unboxed mathematical
  text with proper separation from their tables, consistently in the main
  window and the results pop-out.
- **Method help**: every option in every analysis dialog now provides working,
  keyboard-accessible help.
- **Graph Studio**: running analyses can be cancelled, and very large graphs
  produce a clear warning or are safely blocked instead of freezing the app.
- **Performance and packaging**: smaller application bundles for faster
  loading, and hardened macOS packaging.

## Platforms

- macOS 13 or later, Apple Silicon (`arm64`). Intel Macs are not supported by
  this build.
- Windows 10/11, x64.
- Windows 11, ARM64.

## Beta limitations

- This build is prerelease software and may contain defects.
- The macOS build is locally signed but not Apple-notarised, so macOS may show
  an unidentified-developer warning.
- The Windows installers are not yet code-signed, so SmartScreen may show a
  warning. Verify the SHA-256 before proceeding.
- There is no automatic update channel; future betas must be installed
  manually.
- Important analyses and conclusions should be independently reviewed.

## Verify the downloads

| File | Size (bytes) | SHA-256 |
| --- | --- | --- |
| `OpenStats-Studio-Beta-0.1.1-macOS-Apple-Silicon.dmg` | 298,610,881 | `e029105811c671810e3909603eb64f06351030499c4b8e1213f198148aa42e34` |
| `OpenStats-Studio-Beta-0.1.1-Windows-x64-setup.exe` | 227,184,405 | `7ce6660d5f6eb13c516aac790f2e3db193eb21b44b406669af803174aa8056de` |
| `OpenStats-Studio-Beta-0.1.1-Windows-ARM64-setup.exe` | 226,976,108 | `c683a0aaa93d8b746f96d36452efe4eeb8255e2ac17f7d527995a32047761548` |

Please report beta feedback through this repository's Issues section without
including confidential data.
