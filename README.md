<div align="center">
  <img src="public/kanigara-icon.svg" alt="Kanigara Bloom icon" width="112" height="112" />
  <h1>Kanigara Bloom</h1>
  <p><strong>Your everyday file tools, one sunflower away.</strong></p>
  <p>Meet Kanigara Bloom, your pixel-art desktop companion for Windows.<br />Merge PDFs, convert images, and turn documents into PDFs — right from its petals.<br />Local tools first. Optional AI when you need it.</p>
  <p>
    <img alt="Windows 10 / 11" src="https://img.shields.io/badge/Windows-10%20%2F%2011-357EC7?style=flat-square" />
    <img alt="Tauri 2" src="https://img.shields.io/badge/Tauri-2-E6B138?style=flat-square" />
    <img alt="React" src="https://img.shields.io/badge/React-19-61DAFB?style=flat-square" />
    <img alt="TypeScript" src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square" />
    <a href="LICENSE"><img alt="MIT License" src="https://img.shields.io/badge/License-MIT-78A45A?style=flat-square" /></a>
  </p>
  <p><a href="#less-file-juggling-more-doing">Features</a> &middot; <a href="#convert-or-merge-files">File tools</a> &middot; <a href="#meet-kanigara-bloom">Meet the companion</a> &middot; <a href="#build-from-source">Build from source</a></p>
</div>

## Less file juggling. More doing.

Keep your file tools beside your work. Drop files onto Kanigara Bloom, choose an action, and save the result. No AI account or API key is needed for local file tools.

| Bring your files | Choose your action | Keep control |
|---|---|---|
| Drag onto Kanigara Bloom or browse your computer | Merge PDFs, make image PDFs, convert images or export Office documents | Review the input order and choose a new output file; originals stay unchanged |

### File tools

- **Drop Actions:** merge PDFs, turn PNG/JPG/WebP images into a PDF, convert one image between PNG/JPG/WebP, or export one DOCX/XLSX/PPTX to PDF using installed Microsoft Office.
- **Petal action menu:** a compact flower with clear action icons for Merge PDFs, Images to PDF, Convert image and Office to PDF. Navigate with arrows, number keys, Tab and Enter; Escape or the close button dismisses the menu.
- **Desktop companion:** drag Kanigara Bloom inside the monitor work area, choose 1x/2x/3x scaling, preview six expressions, or hide it through the hover button, tray or shortcut.
- **Optional taskbar walking:** enable or disable **Walk along taskbar** in General. Hands and feet move while walking. Animation and reduced-motion controls remain available.
- **Auto-sleep:** after three minutes without interacting with Bloom, an idle Kanigara Bloom closes its eyes, breathes slowly with floating Z letters on a transparent background and stops walking. It can sleep while you work in other apps. Clicking, dragging, using a Bloom shortcut or dropping files wakes it; active file operations keep it awake. Reduced motion uses a still sleep pose.
- **Local preferences:** appearance, shortcuts, startup choices and position are stored locally. UTF-8 settings files with or without a BOM are accepted.
- **Separate AI Provider settings:** this category currently reports the disconnected state. Provider sessions, live AI progress and approvals are not implemented.

## Convert or merge files

1. Drop supported files on Kanigara Bloom or its open petal menu. Alternatively, choose a file action petal, then **Choose files** to browse your computer.
2. Review the file list. Move files up or down to set PDF/image page order, or remove unwanted files.
3. Choose an available action and click **Choose output & merge/convert**.
4. Pick a new output filename. Bloom reports the saved path after writing succeeds.

Files are processed locally. Inputs stay unchanged, and existing output files are rejected rather than overwritten.

| Input | Available action |
|---|---|
| Two or more PDFs | Merge in the selected order |
| One or more PNG/JPG/WebP images | One image per A4 PDF page, keeping aspect ratio |
| One PNG/JPG/WebP image | Convert to PNG, JPG or WebP |
| One DOCX/XLSX/PPTX document | Export to PDF through desktop Word, Excel or PowerPoint |

**Limits:** up to 20 inputs, 25 MiB per input, 100 MiB total, 500 merged PDF pages and 40 megapixels per image. Unsupported or corrupt files produce an error.

**Office export:** requires the corresponding installed Microsoft Office application. Close that application before exporting so Bloom does not affect your open documents. Macros are disabled and Word/Excel link updates are disabled. Office licensing, protected-view or password dialogs may prevent unattended export. Only DOCX, XLSX and PPTX are supported.

Office export times out after three minutes. Close any leftover Office dialog before retrying.

**PDF merge:** preserves source page trees, including inherited page sizes, resources and rotation. Password-protected PDFs and PDFs containing forms or signatures are rejected. Bookmarks are not retained. PDF compression, splitting, OCR and PDF-to-image conversion are not included.

## Meet Kanigara Bloom

The sunflower companion keeps its aviator goggles, red scarf and leaf hands and feet.

| Idle | Working | Needs approval | Success | Error |
|---|---|---|---|---|
| ![Idle preview](.github/assets/state-idle.png) | ![Working preview](.github/assets/state-working.png) | ![Approval preview](.github/assets/state-needs-approval.png) | ![Success preview](.github/assets/state-success.png) | ![Error preview](.github/assets/state-error.png) |

These are expression previews under **Settings > Appearance**. They do not imply a connected AI provider or running approval system.

Sleeping is the sixth expression. It reuses Kanigara Bloom's existing closed-eye pose with a small breathing movement. Inactivity is measured only from interaction with Bloom; the app does not monitor your keyboard or mouse in other applications.

## Controls

| Action | Default control |
|---|---|
| Open petal menu | Click Kanigara Bloom, or Ctrl + Alt + M |
| Open Settings | System tray menu only |
| Show / hide companion | Ctrl + Alt + K, left-click tray icon, or tray menu |
| Move Kanigara Bloom | Drag the character |
| Open file actions | Drop files on Kanigara Bloom, or choose a file action petal |
| Enable / disable walking | Settings > General > Walk along taskbar |
| Change global shortcuts | Settings > Shortcuts |
| Dismiss menu / Settings | Escape or close button |

Shortcut conflicts are reported in Settings. Tray controls remain available if a hotkey cannot be registered.

## What grows next

Bloom is being built around local productivity. AI is an optional module in that product.

| Planned feature | Purpose |
|---|---|
| Context Capsule | Save and reopen a workspace's folders, apps, URLs and notes |
| Action Chains | Run explicit sequences of local actions |
| Smart Selection | Act on selected text, links, code and paths |
| More Drop Actions | Batch rename, compression, JSON formatting and folder analysis |
| Adaptive Paste | Transform clipboard content into a chosen format |
| Quick Capture | Save and search notes, URLs and snippets |
| Workflow Recovery | Reopen explicit workspace checkpoints |
| Optional AI | One active provider, quick chat, real task events and explicit approvals |

These roadmap entries are not available yet. The core productivity features are intended to work offline without AI login. Provider integrations and approvals will be added separately.

## Build from source

Built with Rust, Tauri 2, React, TypeScript and Canvas 2D. PDF/image operations use `lopdf` and `image`. File selection uses native Windows dialogs; Office export uses a local PowerShell helper.

A downloadable installer is not published. Feature availability depends on the build; the latest file tools described above are not yet included in the code on `main`.

Prerequisites: Node.js/npm, Rust, and the Windows Tauri build requirements (MSVC C++ build tools and WebView2).

```sh
npm ci
npm run tauri dev
```

Validation:

```sh
npm test
npm run build
cd src-tauri
cargo test
cargo fmt --check
```

Build a debug executable without an installer from the repository root:

```sh
npm run tauri build -- --debug --no-bundle
```

Native drag/drop, Office export, Acrylic composition and physical monitor/DPI changes need Windows testing; passing unit tests alone does not verify those integrations.

## License

[MIT](LICENSE) Â· 2026 kanigaraa
