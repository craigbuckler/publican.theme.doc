---
title: Changing JavaScript
description: How to alter the client-side JavaScript functionality.
date: 2026-03-06
author: Craig Buckler
tags: Publican, theme, JavaScript
priority: 1.0
---

This theme's JavaScript files are bundled by [esbuild](https://esbuild.github.io/).


## `main.js`

`main.js` is the root entry script which `import`s others from the `lib` sub-directory:

* `lib/theme.js` -- handles theme switching
* `lib/share.js` -- handles social sharing button

You can add, remove, or rearrange JavaScript files as necessary.

> The template partial `src/template/_partials/htmlhead.html` sets a Content Security Policy in the HTML `<head>`. You may need to update the `<meta>` tag if you load resources from third-party domains.

Note that JavaScript is not configured to be hot-reloaded. You must manually refresh the browser when a change is made.
