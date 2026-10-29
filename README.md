# Affinity Wall (offline browser tool)

`offline-browser-tool.html` is a single-file tool for UX research synthesis. You import session transcripts (VTT or SRT) and recordings (MP4), pull and code quotes, grab video frames for context, and cluster everything into an affinity diagram. It then produces a findings report.

It runs entirely in your browser from a file on your computer. It has no install, no account and no network connection.

## Getting started

1. Open `offline-browser-tool.html` in **Chrome or Edge**. Double-click it, or drag it onto a browser window. Firefox and Safari also work, with limits; see [Browser support](#browser-support).
2. The tool opens on a made-up example study. Click **Import files** to start your own; importing replaces the example.
3. Choose your transcripts and recordings together, or drag them onto the page. A transcript and a recording with matching file names are paired automatically.
4. In the review dialog, check each session's label (for example P1), which speaker is the researcher, and which recording goes with each transcript. Then click **Add**.
5. Press **Ctrl+S** (**⌘S** on a Mac) to save a project file. Do this often. Nothing is saved automatically.

## Workflow

### Transcripts

- **Pull a quote:** select words in a transcript and click **Pull quote** in the toolbar that appears, or press **Q**. The toolbar also has one-click buttons for your most recently used codes.
- **Play from a turn:** click a turn's timecode to play the recording from there. The transcript follows along as it plays.
- **Add an observation:** press **O** or click **Add observation** while watching. This creates a card at the current moment with a frame from the video. Use it for things you saw rather than heard.
- **Find words:** use the search box to find words in the current transcript.
- **Fix a typo:** hover over a turn and click **Edit**. See [Fixing transcript typos](#fixing-transcript-typos).

### Cards

Clicking a card opens its panel. From there you can:

- play the recording from that moment, and adjust the time by −5, −1, +1 or +5 seconds
- click **Grab this frame** to attach a snapshot
- edit the quote and add a context note
- turn codes on or off; **1–9** toggles the first nine codes
- move the card to a group

### Board (affinity diagram)

- **Arrange cards:** drag cards from **Unsorted** into groups (blue labels), and drag groups under themes (pink labels).
- **Start a group:** drop cards on a **New group** tile.
- **Move several cards at once:** Shift-click to select several cards, then drag them together.
- **Filter:** filter by participant, code or text. Cards that don't match are dimmed.
- **See who's behind a group:** each group shows which participants it came from.
- **Undo:** **Ctrl+Z / ⌘Z** undoes moves, code changes, deletes and transcript edits.

### Report

The **Report** view shows:

- which participants contributed to each group
- findings grouped by theme and group, with quotes, attributions and snapshots
- code counts per participant

From there you can:

- **Copy report** and paste it into a doc or slides
- **Download report** as a standalone HTML file with images and fonts embedded
- **Download CSV:** one row per card. For FigJam, import the CSV, select the *Sticky note* column, and run *Convert to stickies*.
- **Copy as table** to paste straight into Google Sheets or Excel

## Saving and opening

| Action | How |
|---|---|
| Save | **Ctrl+S / ⌘S**, or the **Save** button |
| Save to a new file | **More → Save as…** (Chrome and Edge only) |
| Open a project | **More → Open project file…**, or drag the `.affinity.json` file onto the page |

- **Nothing is saved automatically.** Closing or reloading the page discards unsaved changes. The header shows **Unsaved changes** and the Save button shows a dot until you save.
- **In Chrome and Edge,** the first save asks where to put the file. After that, Save writes to the same file each time. A project opened with **Open project file…** also saves back to itself.
- **In Firefox and Safari,** each save downloads a new copy of the project file.
- **The project file holds:** transcripts, cards, codes, groups, themes, snapshots and transcript edits.
- **It doesn't hold the recordings.** After opening a project, drop the MP4s onto the page again. They're matched to their sessions by file name.

## Fixing transcript typos

1. Hover over a turn and click **Edit**. Each box is one caption from the VTT.
2. Fix the text, then press **Enter** to finish, or **Esc** to cancel.
3. Edited captions are underlined with dots. Hover over one to see the original wording.

If a quote card contains the same words, the fix is applied to the card as well.

**Writing fixes back to the original VTT** (Chrome and Edge): when you save, the tool also updates the transcript files you imported during this sitting, either through **Import files** or by dragging them onto the page. The first time, the browser asks permission to edit each file.

- Only the text of the captions you edited changes. Timings, caption numbers, speaker names, line endings and everything else in the file stay exactly as they were.
- If the file changed since you imported it, the tool doesn't write to it and tells you.
- Files that aren't saved as UTF-8 text, and auto-generated rolling captions (where each line repeats the line before), aren't rewritten.

**After reopening a project,** the tool no longer has access to the VTT files. Click **Update P1's file…** in the notice and pick the original file, or drag the VTT onto the page again.

**In Firefox and Safari,** your fixes are kept in the project file. Use **Download corrected transcript** in the session panel to get a corrected copy.

## Privacy and security

- **No network access.** The file includes a security policy that tells the browser to block every network request. Even a bug in the tool couldn't send anything out. Its fonts are built into the file.
- **Nothing is stored in the browser.** The tool uses no cookies, local storage or IndexedDB. Your work exists only in the open page and in files you save.
- **Recordings never leave your disk.** The browser plays them directly from the file and never uploads or copies them.
- **Files are written only when you act:** saving, exporting, or a transcript write-back you've given permission for.
- **Opened project files are checked field by field before anything is shown,** so a tampered file can't run code in the page.
- **CSV exports neutralize spreadsheet formulas.** A cell starting with `=`, `+`, `-` or `@` gets a leading apostrophe.

### What to watch for when sharing

- **Project files contain full transcripts,** including the speaker names from your VTTs.
- **Reports and CSVs use display names instead.** Set them in **Session settings**, for example to show "P1" instead of a real name. Names said aloud in quotes still appear.
- **Files aren't encrypted.** Keep project files somewhere as secure as your recordings.

## Keyboard shortcuts

| Key | Action |
|---|---|
| Ctrl/⌘ S | Save the project |
| K | Play or pause |
| J / L | Back or forward 5 seconds |
| Q | Pull the selected words as a quote |
| O | Add an observation at this moment |
| 1–9 | Toggle a code on the open card |
| Shift-click | Select several cards on the board |
| Delete | Delete the selected cards |
| Ctrl/⌘ Z | Undo |
| Esc | Close the card panel, or cancel a transcript edit |

## Browser support

| | Chrome / Edge | Firefox | Safari |
|---|---|---|---|
| Import, code, cluster, report | Yes | Yes | Yes |
| Play Zoom and Teams MP4s | Yes | Yes | Yes |
| Save to the same file each time | Yes | No, downloads a new copy | No, downloads a new copy |
| Write transcript fixes into the original VTT | Yes | No, download a corrected copy | No, download a corrected copy |

## File formats

- **Transcripts:** WebVTT (`.vtt`) and SubRip (`.srt`). Speaker names are read from Zoom-style `Name: text` lines, Teams-style `<v Name>` tags and `[Name]` prefixes.
- **Recordings:** MP4, MOV, M4V and WebM video, and M4A, MP3 and WAV audio. Audio-only sessions can't have frames grabbed.
- **Project files:** `.affinity.json`. The tool also opens project files from the version of the tool hosted in the Claude app.

## Troubleshooting

- **A recording won't play:** the browser can't decode that file, which happens with some MOV or HEVC recordings. Try Chrome or Edge, or convert the file to an H.264 MP4.
- **"Recordings aren't part of the project file":** drop the MP4s onto the page again to relink them.
- **The transcript file wasn't updated:** read the message shown after saving. Most often the file changed since import, or permission wasn't given. Use **Update P1's file…** to try again, or **Download corrected transcript**.
- **Grab this frame says the video isn't ready:** let the video load or play for a moment, then try again.