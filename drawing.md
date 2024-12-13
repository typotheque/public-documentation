# Outline Drawing

The two main designer responsibility is to [name the glyphs](https://github.com/typotheque/public-documentation/blob/main/designer-orientation.md) correctly, and to draw the shapes correctly. Glyphs app as a useful tutorial about [drawing outlines](https://glyphsapp.com/learn/drawing-good-paths) and we suggest that you read it. They also have recommendation about [naming glyphs](https://glyphsapp.com/learn/getting-your-glyph-names-right). FontLab also [published some drawing recommendation](https://help.fontlab.com/fontlab-vi/Contours/#terminology), and GoogleFonts maintains their [Outline Quality](https://googlefonts.github.io/gf-guide/outlines) requirements.   

Here are additional information about drawing outlines.

## Contours must be always closed
<img width="571" alt="image" src="https://github.com/user-attachments/assets/4c09a1ed-799a-4b9a-bfcc-0d1bd6d15eea" />

## Contour direction
Filled outlines must be drawn anti-clockwise. While both drawings will appear identical in the font editors, text engines will render clockwise outlines lighter than anti-clockwise outlines. 

<img width="616" alt="image" src="https://github.com/user-attachments/assets/360d07e0-8809-4b7b-8a25-dc70ab2c9043" />

Use this Typotheque internal script to identify contours which have wrong direction. Glyphs > Path > **Correct Path Direction** will fix it.

## Outline compatibility
When drawing multiple masters, outlines need to be compatible for interpolation, including anchors. Make sure you check compatibility within Glyphs app, by settingup a custom parameter **Enforce Compatibility Check** Read more about [Glyphs Multiple Masters tutorial](https://glyphsapp.com/learn/multiple-masters-part-2-keeping-your-outlines-compatible) on how to keep your outlines compatible.

<img width="658" alt="image" src="https://github.com/user-attachments/assets/f03dbbad-33d5-43ff-9c6e-171bd2a32ff6" />

Use this Typotheque internal script to check interpolation confidence.

## Overlapping contours
Early in the design stage you can construct glyphs by overlapping contours. However, when you deliver the glyphs ready for production, overlapping contours at the outer positions (very top, bottom, left or right) will cause rendering issues in the Variable fonts.

<img width="607" alt="image" src="https://github.com/user-attachments/assets/94acda5f-9ef4-4e25-9b7a-cb883cc0b930" />

Overlaps not in the outer positions is acceptable. 
<img width="586" alt="image" src="https://github.com/user-attachments/assets/4574d03f-447c-45f4-8636-8f6f8b4f9e3b" />

## Open corners
While Glyphs app allows creating inner and outer white corners, you should avoid using outer white corners

<img width="612" alt="image" src="https://github.com/user-attachments/assets/6a00b5db-aa57-43aa-8ae5-eb47ac5397a3" />

## Contour problems
Overlapping BCPs will cause export error. Sometimes it is hard to detect such issue such as overlapping BCPs in streight segments.
<img width="585" alt="image" src="https://github.com/user-attachments/assets/1595b87b-0df5-44b1-adcd-854755b4efaa" />

Missing BCPs will give unpredictable results when converting outlines to quadratic curves (TrueType outlines). 
<img width="564" alt="image" src="https://github.com/user-attachments/assets/6a02e1e9-0041-422f-a03e-611577a09351" />

Test fonts always by exporting to various formats:
- PostScript CFF (static fonts)
- TrueType (static fonts)
- Variable fonts (ttf)

Every of these exporting options may give different results, so it is important that you ensure that there are no exporting errors in your source file.

## Points in extremas
In order to allow use hinting, points should be placed at the x and y extramas of your paths. This is important for upright fonts, and less important in italic and slanted fonts. Glyphs App allows to insert points at extrams using this function Paths > Add Extremes.

Hints are either vertical or horizontal, so they can only get hooked on nodes at the extremum of one curve. Also, by having them you could control better the curves and probably reduce the need for extra nodes.

Glyphs plugins to check quality of outlines
- Jens Kutílek’s Red Arrow
- Simon Cozens’ Heatmap
- Mekkablue Path Problem Finder

## Transformed components
When components are scaled, rotated or mirrored, it will cause problem when generating variable fonts. Avoid tranforming components. Flipping components also changed outline direction , when components is decomposed, and will render differently.

## Drawing for slanting
Drawing strategies that work for upright fonts don't work well for the slanted styles. Especially when there is a variable slant axis. For example drawing on the left would resutl in visible kink when stems connect to the curve. That's why it is safer to draw it as on the example on the right.

<img width="613" alt="image" src="https://github.com/user-attachments/assets/85fdd418-a29d-4137-8105-625777a4eb6b" />



   
