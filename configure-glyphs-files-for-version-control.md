# Configure Glyphs files for version control

The “last change” timestamps of glyphs pollute git history. To disable them:

- Glyphs 2: add font-level custom parameter `Disable Last Change` and _check_ it.
- Glyphs 3: add font-level custom parameter `Write lastChange` and _uncheck_ it.

## Glyphs 3 only

Use the version 3 format, as long as all collaborators on the source file already use Glyphs 3:

- In the “Other” tab of the “Font Info” window, choose “Version 3” for “File Saving”.

The test texts inside edit tabs are saved to the file by default. Unless you really need other people to see your last used test texts, disable this behavior to avoid unnecessary changes in git history:

- Add font-level custom parameter `Write DisplayStrings` and uncheck it.

If a UFO-like experience of per-glyph version control is desired (eg, changing a glyph name doesn’t shift hundreds of lines of the whole .glyphs file), use the `.glyphspackage` format:

- Save as a new file, with the file format “Glyphs File Package”.
