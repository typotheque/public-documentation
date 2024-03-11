# Configure Glyphs files for version control

> These instructions are specific to Glyphs 3.

1. Use the version 3 format:

    - In the “Other” tab of the “Font Info” window, make sure “Version 3” is chosen for “File Saving”.

2. Use the “.glyphspackage” format for UFO-like, per-glyph version control:

    - Save as a new file with the file format “Glyphs File Package”.

3. The “last change” timestamps pollute Git commits. To disable them:

    - Add font-level custom parameter “Write lastChange” and _uncheck_ it.

4. The test texts inside edit tabs are saved to the file by default. Unless you really need other people to see your last used test texts, disable this behavior to avoid unnecessary changes in Git commits:

    - Add font-level custom parameter “Write DisplayStrings” and _uncheck_ it.
