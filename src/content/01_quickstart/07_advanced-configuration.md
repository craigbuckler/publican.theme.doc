---
title: Advanced site configuration
menu: Advanced configuration
description: How to change the publican.config.js file.
date: 2026-03-06
author: Craig Buckler
tags: Publican, theme, configuration
priority: 1.0
---

The site build is configured by the `publican.config.js` file. It contains JavaScript code to:

* load and parse values set in the [`.env.dev` and `.env.prod`](--ROOT--quickstart/basic-configuration/) configuration files
* [modify page slugs](https://publican.dev/docs/reference/publican-options/#slug-string-replacement) to remove the initial number or date
* set the number of pages and sort order for [directory](https://publican.dev/docs/reference/publican-options/#directory-index-pages) and [tag](https://publican.dev/docs/reference/publican-options/#tag-index-pages) index pages
* [copy static files](https://publican.dev/docs/reference/publican-options/#pass-through-files) such as images and icons
* run [event hook functions](https://publican.dev/docs/reference/event-functions/) to examine and modify data
* append [custom global values and functions](https://publican.dev/docs/reference/global-properties/#custom-global-properties) to the `tacs` object
* define [replacement strings](https://publican.dev/docs/reference/publican-options/#string-replacement) such as [`−−ROOT−−`](--ROOT--blog/updating-content/#adding-links)
* [minify HTML](https://publican.dev/docs/reference/publican-options/#html-minification) in production mode
* [clean the build directory](https://publican.dev/docs/reference/publican-methods/#clean)
* [start the build](https://publican.dev/docs/reference/publican-methods/#build)
* [watch for file changes](https://publican.dev/docs/reference/publican-options/#watch-mode) in development mode
* [start a development mode server](https://www.npmjs.com/package/livelocalhost)

You can add your own Publican customisations as necessary.


## Function libraries

The theme provides the following code libraries in the `lib` directory.

* `hooks.js`: Publican [event hook functions](https://publican.dev/docs/reference/event-functions/)
* `format.js`: date, number, and similar formatting functions
* `nav.js`: navigation generation functions for menus, breadcrumbs, pagination, etc.
