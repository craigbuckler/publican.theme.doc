---
title: Changing CSS styles
description: How to alter the look and feel of the Publican website.
date: 2026-03-06
author: Craig Buckler
tags: Publican, theme, CSS
priority: 1.0
---

This theme's CSS files are bundled by [esbuild](https://esbuild.github.io/).


## `main.css`

`main.css` is the root stylesheet which `@import`s others from the sub-directories:

* `core` -- default element styles
* `components` -- specific components such as the header, footer, titles, etc.

You can add, remove, or rearrange CSS files as necessary.

> The template partial `src/template/_partials/htmlhead.html` sets a Content Security Policy in the HTML `<head>`. You may need to update the `<meta>` tag if you load resources from third-party domains.


## `core/variables.css`

You can change CSS variables defined in `core/variables.css` to modify fonts, layout dimensions, and colors.

Colors are generated and defined using the [CSS `light-dark()` function](https://developer.mozilla.org/docs/Web/CSS/color_value/light-dark) which sets light and dark theme colors.
