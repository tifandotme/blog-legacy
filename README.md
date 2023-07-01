> As of June 2023, this blog has been deprecated in favor of a new blog rebuilt with Next.js. [See the new shiny blog](https://github.com/tifandotme/blog).

## Description

My blog built with Hugo, hosted on Vercel. Blog posts are split into two sections, namely /tech and /personal. 

## Features

### Syntax Highlighting

Make sure to specify language on the fenced code. [List of language code](https://gohugo.io/content-management/syntax-highlighting/#list-of-chroma-highlighting-languages).

### Emoji

- Use this format to insert emojis: `:beer:`, `:face_with_monocle:`.
- [Cheat sheet](https://www.webfx.com/tools/emoji-cheat-sheet/).

### SEO

It's recommended to include `description` in front-matter, since it's used in description meta tag. Otherwise it will use the summary from the post content.

### Taxonomy

- Site contains only 2 taxonomies: techtags, and personaltags
- Both are set up to have a permalink of /tech/tags and /personal/tags.
- Both list and term taxonomy use layout from `taxonomy/list.html`
- /techtags and /personaltags content uses empty.html layout and redirected to the correct url.
- Reference: https://www.hannaliebl.com/blog/nesting-taxonomies-in-hugo/

### Sitemap

- Custom sitemap at `_default/sitemap.xml`
- Add `skipSitemap` (bool) in front-matter to exclude a post from being indexed in sitemap
- [Default template](https://github.com/gohugoio/hugo/blob/master/tpl/tplimpl/embedded/templates/_default/sitemap.xml)

### RSS

- Custom RSS at `_default/rss.xml`

## License

[MIT](https://github.com/tifandotme/blog-legacy/blob/master/LICENSE/)
