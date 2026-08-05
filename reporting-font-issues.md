# How to report a font issue (so we can fix it quickly)

When something looks wrong with a font — a missing character, a unexpected shapes, letters colliding, a font that refuses to install — the fastest way to get it fixed is to help us see exactly what you’re seeing.

The reason is simple: **we can only fix a bug we can reproduce.** The same font can behave differently in Word than in InDesign, on Windows than on macOS, or in version 1.2 than in version 2.0 of the font itself. Without a few key details, we end up guessing.

Here’s what to send us. Don’t worry if you can’t answer every point — send what you can.

---

## The six things we need

### 1. Which font

The full name as it appears in your application, including the style and weight. ‘Zed’ isn’t quite enough; ‘Zed Text Semi-Wide LCG Medium Slanted’, or name of the file (`ZedTextSemiWideLCG-MediumSlanted.otf`) tells us exactly where to look.

### 2. Which version of the font — and where it came from

Fonts get updated, and a bug in one version is often already fixed in the next. Tell us the version number if you can find it (see below), and let us know how you got the font: downloaded from us, or supplied by someone else.

<img width="512" height="577" alt="image" src="https://github.com/user-attachments/assets/9867cf71-e496-49fb-b120-67525ea5e2ad" />


### 3. Which application — and its version

For example: ‘Adobe InDesign 2024, version 19.5’, ‘Microsoft Word for Microsoft 365’, or ‘Google Chrome 126’. In most programs you’ll find this under **Help → About** or, on a Mac, under the application’s own menu → **About**.

### 4. Which environment

Your operating system and its version — ‘Windows 11 Pro, 23H2’ or ‘MacOS 14.5 Sonoma’ — plus anything unusual about the setup, such as a font manager, a shared network drive, a virtual machine or a remote desktop.

### 5. The steps that cause the problem

This is the most valuable part. Write it as a short numbered list, as if you were teaching a colleague to trigger the bug on purpose:

> 1. Open a new document in Word.
> 2. Set the font to Zed Text Semi-Wide LCG Medium Slanted, 12 pt.
> 3. Type the word ‘naïve’.
> 4. The dieresis on the ‘i’ overlaps the letter above it.

Please also tell us whether it happens **every time** or only occasionally.

### 6. What you expected, and what actually happened

A single sentence for each. It sounds obvious, but it often reveals that the ‘bug’ is a setting rather than a fault — which means an instant fix for you.

---

## How to find a font’s version number

**On Windows:** open **Settings → Personalisation → Fonts**, search for the font, and click it. The version is listed on the details page.

**On macOS:** open **Font Book** (in Applications), select the font, and choose **View → Show Font Info**. The version appears in the panel on the right.

**If it came from a service** such as Adobe Fonts, Google Fonts or Monotype, just tell us that — we can look the version up from there.

---

## Extras that help a lot

- **A screenshot or short screen recording.** Please capture the whole application window, not just a crop, and don’t re-type the text into an email — the problem often disappears in the retelling.
- **A small sample file** that shows the issue: a one-page document, a test web page, or a single paragraph.
- **A PDF export**, if the problem only shows up when printing or exporting.
- **Does it happen elsewhere?** If you’ve tried the same font in another application or on another computer, tell us what happened. ‘It’s fine in Illustrator but broken in PowerPoint’ narrows things down enormously.

## In short

The more precisely you can answer *which font, which version, which application, which environment,* and *which steps*, the sooner we can reproduce the problem — and a bug we can reproduce is usually a bug we can fix the same day.

If you’re unsure about any of it, send the report anyway. We’d far rather have a partial report than none at all, and we’ll happily walk you through the rest.
