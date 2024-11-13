# Deliver Glyphs files for version control and production

> These instructions are specific to Glyphs 3.2.

## 1. File format and interpolation model

“Font Info” window → “Other” tab:

- “File format version”: select “Version 3”.
- “Font type”: select “Variable”.

Save as a new file with the file format “Glyphs File Package”.

> The “variable” font type makes Glyphs interpolate masters using the variable font model [instead of the Adobe multiple master model](https://handbook.glyphsapp.com/other-settings/#font-type). The .glyphspackage format allows UFO-like, per-glyph version control.

## 2. Metadata

- Add font-level custom parameter “[Write lastChange](https://handbook.glyphsapp.com/custom-parameter-descriptions/#custom-parameter/Write-lastChange)” and _uncheck_ it.
- Add font-level custom parameter “[Write DisplayStrings](https://handbook.glyphsapp.com/custom-parameter-descriptions/#custom-parameter/Write-DisplayStrings)” and _uncheck_ it.

## 3. Other font info

Go through every tab of the “Font Info” window, and remove any info that’s not relevant to your design, and correct any info that’s wrong.

In particular, for masters, only keep the stem widths of your glyphs. Typically for each master we only need one value for vertical stems and one value for horizontal stems.

Also, remove non-relevant alignment zones (inherited from Latin), and keep only the alignment zones specific to the given scripts. Make sure it is correctly labeled, e.g. `Body Height`, `Thai`.

## 4. Glyphs and kerning

In principle, only keep your own glyphs and remove any external glyphs:

- Any glyphs that are canonically maintained in a separate file are considered **external glyphs**. In production, external glyphs in your file are replaced with the version from the canonical file.
    - For example, Latin and common punctuation mark glyphs copied from the Latin file to a Devanagari file are external glyphs in the Devanagari file.
    - External glyphs that interact with your glyphs due to **composition** or **kerning** do need to remain in your file, and should be marked **brown**.
    - If you need some other external glyphs for **design reference** or **testing**, mark them **dark gray**.
- **Overrides of external glyphs** due to an optimized design or anchoring aren’t external glyphs anymore. Because they are typographical variants of the external glyphs for your script, append your script’s hyphen suffix to their names as a dot suffix.
    - For example, in a Devanagari file, it’s common to have a “space” glyph optimized for Devanagari and a “dottedcirle” glyph that holds the base anchors for Devanagari combining marks. Because Devanagari glyphs have a “-deva” suffix, these overrides of external glyphs should be named “space.deva” and “dottedcirle.deva”. While for Arabic, because the hyphen suffix is “-ar”, the overrides should be named with a “.ar” suffix.

After removing unnecessary glyphs, go to the “Kerning” window → “…” menu → click “Clean up”. This should get rid of all the unused kerning pairs from all masters.

Quickly review the remaining kerning pairs and remove the ones that don’t involve your own glyphs (eg, a Latin pair “VA” in a Devanagari file).

## 5. README.md

Create a README.md file in your script directory. This file is valuable for documenting any detail that’s not self-explenatory in the source files.

In particular, document the meaning of any persisting glyph color marks.
