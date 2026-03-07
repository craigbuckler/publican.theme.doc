---
title: Changing content
description: How to add, edit, and remove website content.
date: 2026-03-06
author: Craig Buckler
tags: Publican, theme, markdown, content
priority: 1.0
---

The following sub-directories define site content:

* `src/content/` provides markdown and other content
* `src/content/css/` provides CSS stylesheets
* `src/content/js/` provides client-side JavaScript functionality
* `src/media/` provides images and icons (copied as [pass-through files](https://publican.dev/docs/setup/pass-through-files/))

Examine these files to see how content is coded.


## Content files

The theme provides content files you can add, remove, or edit:

* home page: `src/content/#index.md`
* section pages: `src/content/**/*`


## Navigation

The menu navigation follows the directory name order, so `01_section-one` comes before `02_section-two`. If you rename `02_section-two` to `00_section-two`, it would appear before `01_section-one`.

The `NN_` value is removed from the path when creating a slug, so pages are rendered to `quickstart` and `section-one` directories in `build`.

Note:

* Index pages are automatically created in all sub-directories of `src/content/`.
* Tag pages are automatically created at `/tag/<name>` which list all the pages with that specific tag. A page listing all tags is defined at `src/content/tag.md`.


## Front matter

[Front matter](https://publican.dev/docs/reference/front-matter/) is contained between `---` delimiters at the top of content files. These are `name: value` pairs which define meta data about the content that can be used in in [templates](--ROOT--quickstart/update-themes/).

```md
---
title: Publican basic theme
menu: Home
description: This is a basic Publican theme you can adapt or use as-is.
template: default.html
priority: 1.0
index: weekly
tags: Publican, SSG, theme, jsTACS
---

The main content...
```


## Adding links

You can link to any page on the site using it's absolute path, such as `/about/`.

However, the `BUILD_ROOT` directory can be set in the [configuration](--ROOT--quickstart/basic-configuration/) so something other than `/` when your Publican site is hosted on a path of another site, such as `/mysite/`. The link to the About page is therefore `/mysite/about/`.

The root path can be inserted into any path using `−−ROOT−−` (defined as a [string replacement](https://publican.dev/docs/reference/publican-options/#string-replacement) in [`publican.config.js`](--ROOT--quickstart/advanced-configuration/)). You can therefore define links in markdown:

```md
[About page](−−ROOT−−about/)
```

or HTML:

```html
<a href="−−ROOT−−about/">About page</a>
```

and `−−ROOT−−` is replaced with the real root value when the site is built. Changing `BUILD_ROOT` will update all links in the site without manual editing.
