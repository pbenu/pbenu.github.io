# Your site

A Jekyll site for GitHub Pages. Three kinds of writing, each with its own
typography: essays and analysis set as prose, poems set as verse with line
breaks preserved.

## Getting it online at pbenu.github.io

The account and the repository already exist. What's left:

1. Unzip this folder on your computer. GitHub can't read a zip file.
2. On the repository page, click **uploading an existing file**.
3. Select everything *inside* the unzipped folder (Ctrl+A / Cmd+A) and drag it
   into the browser. The contents, not the folder itself.
4. Scroll down, click **Commit changes**.
5. **Settings → Pages**. Source: *Deploy from a branch*. Branch: `main`,
   folder `/ (root)`. Save.
6. Wait two to five minutes. The site appears at `https://pbenu.github.io`.

### If you'd rather use your own domain later

Buy the domain, add a file named `CNAME` at the top of the repo containing
just the domain name, then point the domain's DNS at GitHub. Settings → Pages
walks you through the DNS records. The `url:` line in `_config.yml` would
change to match.

## Making it yours

Open `_config.yml` and change the first four lines — title, tagline,
description, author. Then rewrite `about.md`.

## Adding a piece of writing

Add a markdown file to `_essays/`, `_poems/`, or `_analysis/`. Name it
`YYYY-MM-title.md`. Start it with front matter between two `---` lines:

```
---
title: "The title"
date: 2026-10-14
standfirst: "One line under the title. Essays only. Optional."
published_in: "London Review of Books"
---
```

Every field except `title` is optional. `published_in` is there for work that
appeared somewhere else first.

Poems take `epigraph` instead of `standfirst`. Analysis takes `abstract`,
which renders in a tinted block above the text.

Then write below the front matter in markdown. New pieces appear on the home
page and in their section automatically, newest first.

### Poems

Line breaks and indentation are preserved exactly as typed. Blank line between
stanzas. Don't use markdown's two-trailing-spaces trick — it isn't needed here.

### Footnotes

In essays and analysis:

```
The claim in the text.[^1]

[^1]: The note. It collects at the foot of the page with a return link.
```

### Images

Make a folder `assets/images/`, put the file in it, then:

```
![Description of the image](/assets/images/filename.jpg)
```

Add your `baseurl` to the front of that path if you set one.

## Working on it locally (optional)

Not required — you can edit files directly on GitHub. But if you want to
preview before publishing, install Ruby, then:

```
gem install bundler
bundle install
bundle exec jekyll serve
```

The site appears at `http://localhost:4000`.

## What I couldn't verify

I don't have network access to Ruby's package registry, so I wrote and
checked these files but never ran a Jekyll build against them. The Liquid
syntax and structure are checked; a build error is still possible. If the
first deploy fails, GitHub emails you the error and the Actions tab shows the
log — send it to me and I'll fix it.
