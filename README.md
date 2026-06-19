# Chichingpoipoi

**Chichingpoipoi** is a desktop text normalization and QC tool for linguists and NLP/TTS data teams. It converts raw text into speech-ready form — expanding numbers, abbreviations, symbols, currencies, and more — and provides a quality control checker for normalized output. Built with Python and tkinter.

---

## Features

### Normalizer
Converts input text to TTS-ready normalized form with configurable rules:
- Numbers to words (supports Indian and Western numbering systems, ordinals, decimals, years, times, dates)
- Symbols to words (`%` → "percent", `+` → "plus", etc.)
- Abbreviations and acronyms expansion
- Currency code expansion (`INR` → "Indian Rupees") with locale support (India / US / UK)
- Diacritics removal (`é` → `e`)
- Punctuation stripping and spacing fixes
- Partial expansion for units (GB, KB, MB, Gbps, Mbps, Kbps, KG) with configurable expansion percentage
- Custom token expansion
- Output case control: UPPERCASE, lowercase, Sentence case, Title Case, As-is
- Optional spell-check

Supports single-file and batch processing. Batch output includes a detailed normalization report exported as `.xlsx`.

### QC Tool
Quality control checker for normalized text files. Accepts `.txt` and `.xlsx` input. Detects issues including spacing errors, illegal characters, case inconsistencies, and possible spelling issues. Exports QC reports as `.xlsx`.

### Custom Dictionary
User-managed abbreviation dictionary for domain-specific expansions (e.g. `NM` → "Newton metre"). Entries persist across sessions and are saved to `AppData\Chichingpoipoi\custom_dict.json`.

---

## Requirements

- Python 3.10 or higher
- `openpyxl` — for Excel input/output
- `numpy` — used internally by normalization routines

Install dependencies:
```bash
pip install openpyxl numpy
```

---

## Installation

### Option A — Windows Installer (recommended)

Download `Chichingpoipoi_Setup_v2.0.exe` from the [Releases](../../releases) page and run it. No Python installation required.

### Option B — Run from source

```bash
git clone https://github.com/PriyangshuSwarnakar/chichingpoipoi.git
cd chichingpoipoi
pip install openpyxl numpy
python Chichingpoipoi.py
```

---

## Building from Source (Windows)

Install PyInstaller:
```bash
pip install pyinstaller
```

Then build:
```bash
pyinstaller Chichingpoipoi.spec
```

Use the included `Chichingpoipoi.iss` with Inno Setup Compiler to produce the installer from the `dist\Chichingpoipoi\` output.

---

## Usage

Launch the app and use the three tabs:

1. **Normalizer** — paste or load text, configure normalization rules, set output case, and click Normalize. Use Open Folder for batch processing with Excel report export.
2. **QC Tool** — load a file or folder of normalized text, run the checker, and export the issue report as Excel.
3. **Custom Dictionary** — add, edit, or remove custom abbreviation expansions that apply during normalization.

---

## License

All rights reserved. © Priyangshu Swarnakar
