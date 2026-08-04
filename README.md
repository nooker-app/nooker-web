# nooker-web

The public website for [Nook](https://www.nooker.app), an offline-first RSS
reader for macOS and iOS, and its optional publishing feature.

Hand-written HTML and one stylesheet. No build step, no framework, no
JavaScript — the site describes a reader that works offline and a publishing
feature whose output is plain HTML with a feed, and a page that needed a
megabyte of script to say so would be arguing against itself.

## Layout

```text
public/
  index.html          what Nook is
  publishing/         how Nook Plus works, and where writing lives
  email/              every message the service sends, and why
  privacy/            what is stored and what is not
  terms/
  support/            how to get help, and what to include
  404.html
  style.css
  CNAME               the custom domain GitHub Pages serves
```

## Editing

Edit the HTML. Every page shares the same header, footer, and stylesheet by
copy, which is the right trade at seven pages: a generator would be more to
install and understand than the duplication it removes.

## Deploying

Pushing to `main` deploys to GitHub Pages. CI checks that every page parses and
that no internal link points at a file that does not exist, then publishes.

Deliberately not deployed to Nook's own infrastructure: this repository is
public, and credentials able to write to the bucket that holds people's
published pages do not belong in it.

## Not in this repository

Nothing about how the service is built or operated. The public contract that
describes publishing lives in
[nook-plus-protocol](https://github.com/nooker-app/nook-plus-protocol).
