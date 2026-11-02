# Nova Studio & NovaTube — Official Release Portal Design System

## Pass 1: Design Plan & Subject Grounding
- **Subject & Purpose:** An official Android APK distribution, OTA update portal (`version.json`), and studio hub for **NovaTube** — a media player and direct stream/playlist downloader for YouTube, Shorts, TikTok, Instagram, and Facebook.
- **Target Audience:** Arabic-speaking Android users downloading the latest `.apk` or checking release notes, plus app store reviewers (OPPO App Market, Vivo, Xiaomi, Huawei) verifying publisher legitimacy, `app-ads.txt`, and privacy compliance.
- **Primary Job:** Let a visitor download the verified `.apk` in one tap, inspect what changed in the latest version (`v1.3.0`), and give the developer a zero-friction way to publish updates simply by editing `version.json` and replacing `NovaTube_Latest.apk`.

### Color Tokens (6 Named Hex Values)
| Token | Hex | Role |
|---|---|---|
| `--surface-canvas` | `#08090D` | Primary deep obsidian cinema canvas |
| `--surface-elevated` | `#10131C` | Elevated release table, hardware frame, and changelog container |
| `--surface-interactive` | `#171B26` | Interactive tabs, buttons, and version selector rows |
| `--ink-primary` | `#F3F4F6` | Primary Arabic & Latin editorial headline and body text |
| `--ink-secondary` | `#9CA3AF` | Secondary technical descriptions and release metadata |
| `--accent-amber` | `#F59E0B` | Brand signature Nova Amber ( matches `ic_novatube_logo.xml` ) |

### Typography
- **Primary Arabic & UI Sans:** `IBM Plex Sans Arabic` (400, 500, 600, 700) — engineered for technical legibility, crisp Arabic letterforms, and clean tabular alignment.
- **Technical Metadata & Checksums:** `JetBrains Mono` (400, 500) — strictly reserved for `.apk` filenames, SHA-256 hashes, file sizes (`21.2 MB`), and `version.json` inspector.

### Layout & RTL Architecture
- **Asymmetric Two-Column Release Hero (RTL):**
  - Right column (primary reading start in RTL): Brand identity, full-sentence unfragmented Arabic headline, direct `.apk` download action, live version metadata read dynamically from `./version.json`, and verification checksum.
  - Left column (visual anchor): Interactive Android hardware frame demonstrating NovaTube's actual capabilities (16:9 Long Video Player, 9:16 Vertical Shorts mode, and Multi-Quality / Playlist Downloader sheet) so users can test the interface right in the browser before installing.
- **Architectural Release Ledger:** A clean, table-backed release history and update mechanism rather than floating SaaS marketing cards.
- **Built-in Publisher Update Tool (`مولّد ملف التحديثات`):** A subtle utility drawer in the footer allowing the app owner to type a new version number and changelog lines and copy/download the ready-to-upload `version.json` file in seconds.

## Pass 2: Anti-AI-Slop Critique & Revisions
1. **Removed single-word gradient spans in headlines:** The headline is set in solid `#F3F4F6` with deliberate weight contrast rather than coloring one word orange.
2. **Removed emojis (`🚀`, `✨`, `📱`, `🛡️`):** Every icon is a custom 1.5px stroke SVG or authentic platform emblem.
3. **Removed fake numbered cards:** Numbering (`1`, `2`, `3`) is used *only* in the actual 3-step APK installation walkthrough.
4. **Strict `<bdi>` Isolation:** Every version string (`v1.3.0`), resolution (`1080p`), file size (`21.2 MB`), and SHA-256 hash is wrapped in `<bdi>` so RTL punctuation never flips.
