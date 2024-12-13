# Outline Drawing

The two main designer responsibility is to [name the glyphs](https://github.com/typotheque/public-documentation/blob/main/designer-orientation.md) correctly, and to draw the shapes correctly. GLyphs ass as a useful tutorial about [drawing outlines](https://glyphsapp.com/learn/drawing-good-paths) and we suggest that you read it. They also have recommendation about [naming glyphs](https://glyphsapp.com/learn/getting-your-glyph-names-right). FontLab also [published some drawing recommendation](https://help.fontlab.com/fontlab-vi/Contours/#terminology), and GoogleFonts maintains their [Outline Quality](https://googlefonts.github.io/gf-guide/outlines) requirements.   

Here are additional information about drawing outlines.

1/ Contours must be always closed
<img width="571" alt="image" src="https://github.com/user-attachments/assets/4c09a1ed-799a-4b9a-bfcc-0d1bd6d15eea" />

2/ Filled outlines must be drawn anti-clockwise. While both drawings will appear identical in the font editors, text engines will render clockwise outlines lighter than anti-clockwise outlines. 
<img width="616" alt="image" src="https://github.com/user-attachments/assets/360d07e0-8809-4b7b-8a25-dc70ab2c9043" />

Use this Typotheque internal script to identify contours which have wrong direction. Glyphs > Path > **Correct Path Direction** will fix it.

3/ When drawing multiple masters, outlines need to be compatible for interpolation, including anchors. Make sure you check compatibility within Glyphs app, by settingup a custom parameter **Enforce Compatibility Check**

<img width="658" alt="image" src="https://github.com/user-attachments/assets/f03dbbad-33d5-43ff-9c6e-171bd2a32ff6" />

Use this Typotheque internal script to check interpolation confidence.

4/ Overlapping contours
Early in the design stage you can construct glyphs by overlapping contours. However, when you deliver the glyphs ready for production, overlapping contours at the outer positions (very top, bottom, left or right) will cause rendering issues in the Variable fonts.

<img width="607" alt="image" src="https://github.com/user-attachments/assets/94acda5f-9ef4-4e25-9b7a-cb883cc0b930" />

Overlaps not in the outer positions is acceptable. 
<img width="586" alt="image" src="https://github.com/user-attachments/assets/4574d03f-447c-45f4-8636-8f6f8b4f9e3b" />



   
