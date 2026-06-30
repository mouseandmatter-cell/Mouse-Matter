# Mouse & Matter — Site

This is built with Eleventy (11ty). It auto-generates the whole site from the files in `src/`.

## How to add a new blog post (no code, no asking Claude)

1. Go to `src/posts/`
2. Copy any existing `.md` file as a starting point
3. Rename it to your new post's slug, e.g. `my-new-post.md`
4. Edit the top section (the "frontmatter") between the `---` lines:

```
---
layout: post.njk
title: "Your Post Title Here"
excerpt: "One or two sentences that show up in the homepage preview."
date: 2026-07-15
permalink: "/posts/my-new-post/index.html"
---
```

5. Write your post below the frontmatter in plain markdown:
   - `# Title` for the big title (already in frontmatter, skip this)
   - `## Subheading` for section headers
   - Regular text for paragraphs
   - `---` on its own line for a divider
   - `[link text](https://example.com)` for links

6. Save the file.
7. Commit and push to GitHub:

```
git add .
git commit -m "Add new post: my new post"
git push
```

8. Netlify rebuilds automatically. Live in about a minute. That's it — no HTML editing, no homepage editing. The post automatically appears in the Writing section because it pulls from everything in `src/posts/`.

## Local preview (optional)

If you want to see changes before pushing:

```
npm install
npx @11ty/eleventy --serve
```

Then open the local address it gives you in a browser.

## Project structure

- `src/index.html` — homepage (rarely needs editing)
- `src/posts/*.md` — every blog post, one file each
- `src/_layouts/base.njk` — shared site shell (nav, footer, contact form, styling)
- `src/_layouts/post.njk` — wraps blog posts with article styling
- `.eleventy.js` — config, tells Eleventy how to build everything

## Formspree

Contact form submissions go to `https://formspree.io/f/meedbyoj`, connected to mouseandmatter@gmail.com. If this ever needs to change, search for that URL in `src/_layouts/base.njk` and replace it.
