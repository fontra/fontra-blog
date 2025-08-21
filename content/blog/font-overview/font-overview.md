---
title: Fontra news for January – Font Overview
description: Fontra news for January, new features and updates
date: 2025-01-30
tags: fontra
---
This month's big news is that we finally have a font overview. 

We fixed many bugs and implemented many small improvements. The full human-curated list of changes can be found [here](https://fontra.xyz/changelog.html), Even more details can be found on [our main GitHub repository](https://github.com/fontra/fontra).

### Font overview

A font overview is an essential component for a font editor, especially when it comes to designing a full Latin typeface of any other script that has a relatively small number of glyphs (say less than 5000). 

Fontra’s development was initially guided by Black Foundry’s needs for big CJK projects, in which character sets are managed separately. A font overview wasn’t an immediate priority. But now that we have achieved most of the essential parts for CJK font design, we are able to move forward and improve Fontra for broader font development.

<img src="./font-overview-workspace.png" alt="Screenshot of Fontra's Font Overview">

When opening or creating a font with Fontra, the default view is now the font overview. Double-clicking glyphs in the overview leads the user to an editor view.

*Pro tip: one can open multiple tabs or windows for the same font, by copying the URL into a new tab or window. It is possible to have multiple font overviews or glyph editors open for the same font.*

The left sidebar contains several user interface elements to help viewing the glyphs in the font in an organized way. For example, one can group the glyphs by script. The sections in the overview are collapsable. Alt-click on a section header collapses all sections. Or expands all, if all are collapsed.

Glyph *filtering* is still somewhat limited: while you can quickly filter by glyph name in the search box, we anticipate additional filtering options in the future. We notice that early adopters are enthusiastically proposing additional features.

The documentation for the font overview [is being written](https://docs.fontra.xyz/reference/font-overview/workspace/), and will be enhanced.

In general, the options provide a "view" on the font's collection of glyphs. Changing the options does not change anything about the font itself, just *how we look at it*.

### Glyph sets

A "Glyph set" is a collection of glyphs, which is *independent* from the glyphs that are defined in the font. A glyph can be defined in the glyph set, but not in the font or vice versa. Glyphs in the set that do not exist in the font are represented as "placeholder" glyphs in overview, showing a generic character in gray if the code point exists.

In the left sidebar, there are two sections about glyph sets: 

- "Project glyph sets": belong to the font, and are stored with the font data.  
- "My glyph sets": belong to the user, and are stored locally in the browser.

The "Project glyph sets" contains one special glyph set "This font's glyphs", that represents the glyphs that exist in the font, and nothing more.

Selecting multiple glyph sets shows the *superset* of all selected sets.

Glyphs sets are stored purely by references to online resources. A glyph set can reference any publicly visible text file containing glyph names, or a TSV/CSV file, containing code point and/or glyph name columns. Links to Google Docs or Google Sheets are internally converted to .txt or .csv download links, respectively.

We are considering supporting uploading of local files in the future, but for now consider this a pilot, where we encourage people strongly to use (and create) online glyph set resources.

The currently bundled preset glyph sets collections are from Google Fonts, Black Foundry, Adobe and Christoph Koeberlin. We are [open to suggestions](https://github.com/fontra/fontra/discussions/1943) for more preset glyph sets.

To add one or more glyph sets to either section, use the "+" button. This leads to a dialog where you can either activate any of the preset glyph sets, or add a custom glyph set.

<img src="./preset-glyph-sets-dialog.png" alt="Screenshot of the Fontra Add/remove preset glyph sets dialog">

### Custom glyph sets

To create a custom glyph set, click the "Add custom glyph set" button in the above dialog. This leads to a different dialog, where the user can specify the parameters for a custom glyph set.

We currently support two formats:

- A text file containing white-space separated glyph names  
  - Code points are inferred from the glyph name  
- A tab-, comma-, or semicolon-separated text file (.tsv or .csv) with at least one column  
  - Optionally a header row: the first non-empty, non-comment row  
  - A column can be specified by header cell or by zero-based column index  
  - The code point column can contain decimal or hexadecimal code points.  
  - Hexadecimal code points may be prefixed by `0x` or `U+`  
  - If there is no code point, a code point will be inferred from the glyph name  
  - If there is no glyph name, a glyph name will be inferred from the code point

Additional info for both formats:

- For now, code point and glyph name "guessing" is done according to the Glyphs app naming convention, and will additionally parse `uni1234`\-style and `u12345`\-style names.  
- Both formats support an optional comment character for comment-until-the-end-of-the-line-style comments.

### Font overview further development

In the future, it will be possible to copy/paste glyphs in the font overview, as well as to create and delete glyphs.

### Serverless Fontra

In other news, Simon Cozens is experimenting with a so called "serverless" version of Fontra, that runs entirely in the browser. This is leading to some refactoring of our frontend code, that will be generally beneficial to the project. It makes some of Fontra's *intended* modularity more *practically* modular.

We are very excited by these new possibilities, and we would like to point out that this *diversifies* Fontra's deployment options even more. It is not intended as a replacement of Fontra's already varied set of deployment options. As a quick reminder: There is Fontra Pak (our desktop application), but Fontra can also be run from the command line in a Terminal program. Additionally we have an SQL-based shared storage solution. A new collaborative Fontra server is under construction. Fontra truly is a multi-headed beast, in all the good senses\!

### Other ongoing work

While we can read .glyphs and .glyphspackage data, so far we weren't able to write these formats. We are working to implement that, so people can edit .glyphs and .glyphspackage files directly with Fontra, without the need for conversion.
