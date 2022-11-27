---
title : "README"
description : "README.md content from https://github.com/tifandotme/tifan.me"
skipSitemap : true
---

[![Build status](https://github.com/tifandotme/tifan.me/actions/workflows/gh-pages.yml/badge.svg)](https://github.com/tifandotme/tifan.me/actions/workflows/gh-pages.yml)

# About This Site

**tifan.me** blog posts is split into 2 sections, namely /tech and /personal.

- This readme can be accessed at [tifan.me/readme](https://tifan.me/readme)
- Repository at [github.com/tifandotme/tifan.me](https://github.com/tifandotme/tifan.me)

# Syntax Highlighting

```go
<code>
```

- After fenced code, specify language, otherwise no syntax highlighting.
- [List of language code](https://gohugo.io/content-management/syntax-highlighting/#list-of-chroma-highlighting-languages)

# Emoji! :beer:

- [Emoji Cheat Cheet](https://www.webfx.com/tools/emoji-cheat-sheet/)

# SEO

- meta description needs "description" from front matter, if not found it will use the summary. It's better to set description, especially on a branch list page. 

# Taxonomy

- Reference: https://www.hannaliebl.com/blog/nesting-taxonomies-in-hugo/
- Site contains only 2 taxonomies: techtags, and personaltags
- Both are set up to have a permalink of /tech/tags and /personal/tags.
- Both list and term taxonomy use layout from `taxonomy/list.html`
- /techtags and /personaltags content uses empty.html layout and redirected to the correct url.

# Sitemap

- Custom sitemap at `_default/sitemap.xml`
    * I have added `{{- if not .Params.skipSitemap }}`
    * So, add skipSitemap (bool) front matter to exclude content from being indexed in sitemap
- [Default template](https://github.com/gohugoio/hugo/blob/master/tpl/tplimpl/embedded/templates/_default/sitemap.xml)

# RSS

- Custom RSS at `_default/rss.xml`
    * I have changed the default **.Summary** to **.Description**
- RSS applied to any content type, instead of only index
- As of right now, RSS icon on footer linked to index.xml. Even though /section/index.xml is also available
    - Planning to add section-based RSS link in section.