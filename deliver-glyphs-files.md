# Deliver Glyphs files for version control and production

> These instructions are specific to Glyphs 3.2.

1.  Remove unnecessary metadata:

    - Add font-level custom parameter “Write lastChange” and _uncheck_ it.
    - Add font-level custom parameter “Write DisplayStrings” and _uncheck_ it.

> The “last change” timestamps pollute Git commits. The test texts inside edit tabs (“display strings”) are saved to the file by default. Unless you really need other people to see your last used test texts, disable that behavior to avoid unnecessary changes in Git commits.

2. Use the version 3, .glyphspackage format:

    - “Font Info” window > “Other” tab > “File format version”: select “Version 3”.
    - Save as a new file with “File Format”: “Glyphs File Package”.

> The .glyphspackage format allows UFO-like, per-glyph version control.

3. Remove unnecessary glyphs and kerning:

    - In principle, only keep your own glyphs.
    - Latin or common-script glyphs (“external glyphs”, as they are copied from the Latin source file) that interact with your glyphs (eg, due to composition, anchoring, or kerning) need to be kept as well. Mark such external glyphs in brown.
    - If you need some other external glyphs for design reference or testing, mark them in dark gray. We assume such glyphs can be safely ignored in production.
    - After removing unnecessary glyphs, go to the “Kerning” window > “…” menu > click “Clean up”. This should get rid of all the unused kerning pairs from all masters.
    - Quickly review the remaining kerning pairs and remove the ones that don’t involve your own glyphs (eg, a Latin pair “VA”).

4. Clean up and verify other font info:

    - Go through every tab of the “Font Info” window, and remove any info that’s not relevant to your design, and correct any info that’s wrong.
    - In particular, for masters, only keep the stem widths of your glyphs. Typically for each master we only need one value for vertical stems and one value for horizontal stems.

5. Create a README.md file in your script directory:

    - This file is valuable for documenting any detail that’s not self-explenatory in the source files.
    - Document the meaning of any persisting glyph color marks.
