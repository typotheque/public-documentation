# Vertical metrics

Affected fields in font files are listed below. These fields are typically set to be the same across a font family. Note some fields have either fixed or synced values, therefore only four values need to be decided.

[`hhea` table](https://learn.microsoft.com/en-us/typography/opentype/spec/hhea):

- `ascender`
- `descender`
- `lineGap`: always 0

`OS/2` table:

- [`usWinAscent`](https://learn.microsoft.com/en-us/typography/opentype/spec/os2#uswinascent)
- [`usWinDescent`](https://learn.microsoft.com/en-us/typography/opentype/spec/os2#uswindescent)
- [`fsSelection`](https://learn.microsoft.com/en-us/typography/opentype/spec/os2#fsselection) bit 7 (`USE_TYPO_METRICS`): always set
- [`sTypoAscender`](https://learn.microsoft.com/en-us/typography/opentype/spec/os2#stypoascender): synced to `hhea.ascender`
- [`sTypoDescender`](https://learn.microsoft.com/en-us/typography/opentype/spec/os2#stypodescender): synced to `hhea.descender`
- [`sTypoLineGap`](https://learn.microsoft.com/en-us/typography/opentype/spec/os2#stypolinegap): synced to `hhea.lineGap` thus always 0

> In Glyphs, `OS/2.fsSelection` bit 7 is set with font-level custom parameter “Use Typo Metrics”, while other fields are set with master-level custom parameters: hheaAscender, hheaDescender, hheaLineGap, typoAscender, typoDescender, typoLineGap, winAscent, winDescent.

## Default line height and vertical alignment

> Affected fields: `hhea.ascender`, `hhea.descender` (as well as the synced `OS/2.sTypoAscender` and `OS/2.sTypoDescender`).

First decide the following parameters:

- **Default line height ratio**
  - A comfortable line height ratio according to the design intention.
  - 1.2–1.3 is common for Latin, but some non-Latin scripts may need as large as 1.5.
- **Vertical center**
  - Choose a reference point to vertically center in the default line height.
  - It’s a good practice to use 50% of the cap height for Latin designs.
  - Non-Latin designs don’t necessary need a different reference point, because the vertical alignment of Latin glyphs may still be a major concern.

Then we can calculate `hhea.ascender` and `hhea.descender`:

- Half line height (in font units) = \<units per em> x \<default line height ratio> / 2
- `hhea.ascender` = \<vertical center> + \<half line height>
- `hhea.descender` = \<vertical center> - \<half line height>

For example:

- Half line height: 650 = 1000 (units per em) x 1.3 (default line height ratio) / 2
- `hhea.ascender`: 1000 = 350 (vertical center) + 650 (half line height)
- `hhea.descender`: -300 = 350 (vertical center) - 650 (half line height)

## First baseline offset

> Affected fields: `hhea.ascender` (and the synced `OS/2.sTypoAscender`).

Positioning of the first baseline in a multiline layout is often based on `hhea.ascender`. In case the calculated `hhea.ascender` is smaller than the heights of some significant structures (eg, “Ằ” for a project targeting Vietnamese) and causes clipping:

- Increase the “default line height ratio” then recalculate `hhea.ascender` and `hhea.descender`.
- Alternatively, choose a different “vertical center”.

## Clipping area

> Affected fields: `OS/2.usWinAscent`, `OS/2.usWinDescent`.

To control the clipping area in environments like Office Word:

- Set `OS/2.usWinAscent` and `OS/2.usWinDescent` large enough to enclose all the intended usage of glyphs.
- Besides the bounding box of all glyphs, make sure to also take GPOS mark attachment (anchoring) into consideration.

> Note `OS/2.usWinDescent` takes a positive value, in the sense of a distance from the baseline.
