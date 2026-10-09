# ByteArrayEx Decompiler

A dnSpyEx extension that renders managed method bodies as raw bytes — hex dump with IL offsets, RVA and file-offset prefixes, one-click Copy-As in 7 languages, single/bulk export, hex search, entropy analysis, and diff reports.

![Version](https://img.shields.io/badge/version-1.2.0-blue)
![Runtime](https://img.shields.io/badge/dnSpyEx-net48_%7C_net10-purple)
![Platform](https://img.shields.io/badge/platform-Windows-lightgrey)

Developed by **Dr.FarFar** — member of the eXeTools family, crafted for the .NET community.
Based on the original ByteArray plugin by n00b.

---

## Features

| Area | What you get |
|---|---|
| **Hex view** | 1–64 bytes per row, uppercase/lowercase, `0x` prefix, grouping, ASCII gutter, Row/IL/RVA/File-Offset prefixes |
| **Copy As** | C#, C, VB.NET, Python, PowerShell, Base64, Hex (continuous + `\x`-escaped) |
| **Export** | Single method (`.bin` + `.txt`) or whole module (`.bin` + `.txt` + `map.csv`) |
| **Search** | Hex pattern with `??` wildcards, regex over hex (500 ms budget) |
| **Analyze** | Entropy + classification, module statistics, forensics verdict |
| **Diff** | Summary in a popup, full Markdown report saved to Desktop |
| **Options page** | Grouped settings (Layout, Hex Style, Row Content, Row Prefix, Debugger, per-menu visibility) with one-click **Reset to defaults** |

---

## Screenshots

![About](screenshots/01-%20About.png)
*About dialog*

![Welcome page](screenshots/02-%20Welcome%20Page.png)
*Welcome page*

![Settings](screenshots/03-%20Settings.png)
*Options page — grouped settings with Reset to defaults*

![Switch language](screenshots/04-%20Change%20To%20ByteArrayEx.png)
*Selecting ByteArrayEx from the language dropdown*

![Main view](screenshots/05-%20Main.png)
*Method body rendered as annotated hex dump*

![Copy As](screenshots/06-%20Copy%20As.png)
*Copy As submenu — 7 formats*

![Export](screenshots/07-%20Export.png)
*Export submenu*

![Search](screenshots/08-%20Search.png)
*Search submenu*

![Analyze](screenshots/09-%20Analyze.png)
*Analyze submenu*

![Diff](screenshots/10-%20Diff.png)
*Diff submenu*

---

## Installation

1. Download the Release archive from the [Releases](https://github.com/BlackHatLab-INC/ByteArrayEx-Decompiler/releases) page.
2. Copy `ByteArrayEx Decompiler.x.dll` into your dnSpyEx `Extensions` folder:
   - `bin\Extensions\ByteArrayEx Decompiler\`
3. Restart dnSpyEx.
4. Select **ByteArrayEx Decompiler** from the language dropdown of any method view.

> Requires dnSpyEx (6.6+ / .NET 10 builds). Windows x64. No extra dependencies.

---

## Usage

- **View bytes:** open any managed method — the body renders as an annotated hex dump with a header (size, RVA, verification line).
- **Right-click a method** for the context menu:
  - `Copy As →` any of the 7 formats
  - `Export →` save `.bin` + `.txt` (Desktop by default)
  - `Search →` find a hex pattern or regex in the method bytes
  - `Analyze →` entropy, statistics, forensics verdict
  - `Diff →` compare against clipboard bytes (Summary popup / Markdown report on Desktop)
- **Options:** `Tools → Options → ByteArrayEx Decompiler` — layout, prefixes, debugger helpers, and per-item menu visibility. Every menu entry can be shown or hidden individually.

---

## Notes

- Read-only by design: the plugin never modifies the analyzed assembly.
- Exports are containment-checked (no path traversal, no symlink escape) and written atomically.
- Large inputs are capped with honest truncation markers instead of silent cutoffs.

## License

Copyright © 2026 Dr.FarFar. All Rights Reserved.

This software is provided for personal use only. Redistribution, modification, or republishing without prior written permission from Dr.FarFar is prohibited.

## Credits

- Dr.FarFar (eXeTools family) — design & development
- n00b — original ByteArray plugin concept
