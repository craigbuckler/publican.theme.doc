---
title: Documentation theme configuration
menu: Configuration
description: How to change the documentation site settings.
date: 2026-03-06
author: Craig Buckler
tags: Publican, theme, configuration
priority: 1.0
---

The theme is configured using two configuration files.


## `.env.dev`

`.env.dev` provides the development build configuration parameters. Change the values below `# site setup` to configure the site:

```ini
# build mode
NODE_ENV=development

# development server port
SERVE_PORT=8282

# content files
CONTENT_DIR=./src/content/

# template files
TEMPLATE_DIR=./src/template/
TEMPLATE_DEFAULT=default.html
TEMPLATE_LIST=list.html
TEMPLATE_TAG=tag.html

# CSS entry
CSS_DIR="./src/css/main.css"

# JS entry
JS_DIR="./src/js/main.js"

# CSS and JS browser target
BROWSER_TARGET="chrome130,firefox130,safari17"

# build directory
BUILD_DIR=./build/
BUILD_ROOT=/

# site title
SITE_LANGUAGE="en-US"
SITE_DOMAIN="https://publican-theme-doc.pages.dev"
SITE_VERSION="1.0.0"
SITE_TITLE="Docs"
SITE_DESCRIPTION="This is a Publican documentation theme you can adapt or use as-is."
SITE_AUTHOR="Your Name"
SITE_AUTHORURL="https://publican-theme-doc.pages.dev/"
SITE_AUTHORX="@yourname"
SITE_WORDCOUNTSHOW=50
SITE_THEMEHUE=270
SITE_THEMECOLOR="#090b10"
```

These values are passed to the main `publican.config.js` script when you run `npm start`. You must stop and restart the server when you make changes.

Note that `SITE_THEMEHUE` is a single value between 0 and 360 on the color wheel. This value alone generates a light and dark theme.


## `.env.prod`

`.env.prod` provides the production build configuration parameters where they differ from `.env.dev`:


```ini
# Overrides .env.dev defaults

# build mode
NODE_ENV=production
```

It should not ne necessary to change this file unless you want different development and production settings. For example, you may want to use the a `BUILD_ROOT` of `/` in development, but `/my-blog/` in production.

Both `.env` files are passed to the main `publican.config.js` script when you run `npm run build`. You must rerun it after making changes.
