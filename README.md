# A course published with Alembic

This repository is the **public copy** of a course made with
[Alembic](https://github.com/wangyu16/Alembic): the source of the course's
website. The course is written and edited in Alembic, and each Publish updates
this copy with the pages the author has marked completed. Nothing private is
ever copied here.

Once the course's own "About this course" page is published, it replaces this
text. The course's settings are in `alembic.json`; this is a plain Git
repository, so it stays usable, buildable and adaptable without Alembic.

## Building the site without Alembic

This repo carries a self-contained build that depends only on the public
`orz-markdown` package (no Alembic code):

```bash
npm --prefix .alembic/build install
node .alembic/build/build-site.mjs    # → ./_site
```

A GitHub Actions workflow (`.github/workflows/build-site.yml`) does the same and
deploys to GitHub Pages. It's **manual by default** (Actions tab → "Build site"
→ Run) so it doesn't conflict with Alembic's own publishing; set
**Settings → Pages → Source = GitHub Actions** first. To make a fork
self-publishing on every push, add `push: { branches: [main] }` to the
workflow's `on:` triggers.
