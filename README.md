[README-int.md](https://github.com/user-attachments/files/33117636/README-int.md)
# Log Compare

Side-by-side, line-by-line comparison of two text/log files, like Notepad++ Compare. Built for comparing **working** and **non-working** log sets. Easy, lightweight and user friendly. Compare logs offline and safely. 
Created by Bryan - Defender for Endpoint.

A single HTML file: no install, works offline, and files are read locally in the browser (nothing is uploaded).

## Use

1. Double-click `LogCompare.html` (opens in Edge or Chrome).
2. Drop the working machine's file on **Left** and the non-working machine's file on **Right** (or click to browse,
   or drop both files at once). It compares as soon as both are loaded.
3. Press **F8** / **Shift+F8** (or **N** / **P**) to jump between differences. Click any line to see both versions
   in full in the detail pane, with the changed words marked.
4. **Save report** writes every difference with its line numbers to a `.txt` file you can attach to the case.

| Color | Meaning |
| --- | --- |
| Yellow row | Changed: the line is on both sides but differs. Changed words are red (left) and green (right). |
| Red row | Only in the left file |
| Green row | Only in the right file |
| Dimmed text | Ignored by the current Ignore options |

## Options

* **Mode**: *Smart align* (default) lines up matching lines, so an extra line in one file doesn't make everything
  after it look different. *Line-by-line* compares line N with line N, strictly.
* **Ignore**: *Timestamps* and *PIDs/TIDs* are on by default, because they always differ between two machines.
  Also *GUIDs*, *Case*, *Whitespace*, and a *custom regex* (for example `ScanRequest #\d+`).
* **Only differences** hides identical lines (with 0, 3 or 10 lines of context). Click a hidden block to expand it.
* **Find** (Ctrl+F) searches both files; Enter / Shift+Enter for next / previous match.

## Notes

* Encodings are detected automatically: UTF-8, UTF-16 with or without a byte-order mark and Windows-1252.
* Accepts `.txt` and `.log` in the file picker; any plain-text file can be dropped.
* Speed: two ~60,000-line MPLog files from different machines compare in about 1 second.
