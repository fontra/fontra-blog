---
title: Welcome to the Fontra blog!
description: A brief history of the project so far
date: 2025-01-29
tags: fontra
---
It was long overdue, but here it is – a blog dedicated to Fontra. We will write about new features, work in progress, and future plans. But first: let's recap what happened previously, and summarize the current state of Fontra.

We have come a long way, and it has been quite the trip already. The first commit to git was done on 14 November 2021. The initial name for the project was "Trafo", but on the second day everything got renamed to "Fontra", after our colleague Fabio Caccamo suggested it.

Fontra started as a proof of concept. We needed fast live interpolation of (deeply) nested variable components, good support for large character sets (tens of thousands glyphs), and low friction collaboration within a medium-sized (up to 15 designers simultaneously) team. These requirements were informed by ongoing custom CJK (Chinese, Japanese, Korean) type-designs at Black Foundry. We needed new tools for this, and we considered these three options:

A new extension for RoboFont (a faster successor to our RoboCJK extension)
A new cross-platform desktop application (using Qt or wxWidgets)
A web application + custom server

We were already using a server with a SQL database to enable smooth collaboration of the team on large scale (CJK) projects), coupled with a RoboFont extension for glyph editing.
A cross-platform solution was to be preferred, and indeed web-browsers are by definition cross-platform, why not build on top of that!

OpenType 1.8 (2016) brought the Variable Font format to the real world, and type-designers had been drawing with several masters (or sources) for a while already: it seemed important to us that the font editor would take these multiple-masters considerations from its very foundations. In other words: we envisioned a  "variable first" approach to font editing.

Some informal trials with JavaScript, HTML and CSS quickly had very positive results – both in terms of potential performance, as well as in developer experience. JavaScript has come a long way since the nineties! Additionally, modern web standards are very powerful and remarkably easy to use. It seemed like a solid choice. Just van Rossum’s long experience with coding in the realm of typography (TTX,  FontTools, FontGoggles) helped to develop a vision and architecture for a new, browser-based font editor, even though he had to learn new skills for the web platform. 

We went from cautious first experimental steps to "proper" development rather quickly, since every step along the way confirmed that we were on the right track to achieve our goals.

### Where are we now?

In early 2025, Fontra is a near-feature-complete font editor.

Highlights include:

- Create fonts from scratch
- Read and write various font source formats
- Read various binary font formats
- Export (variable) TrueType and OpenType
- Add/delete glyphs
- Draw/modify glyphs
- Strong support for (variable) components
- Live interpolation
- Edit the font's designspace (variation axes, etc.)
- Perform glyph edits across multiple sources (masters) simultaneously
- A font overview with support for preset and custom glyph sets, powerful grouping options
- Server to collaborate with a team online

Some stats from our main repository on GitHub:

- 541 stars
- 17 contributors
- 10k+ commits
- 1147 closed pull requests
- 614 closed issues

We still have important work left to do, and in this blog we will regularly keep you up to date with the latest developments. Please follow along with our mission to make Fontra an excellent font editor!
