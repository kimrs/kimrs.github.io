# kimrs.github.io

Personal blog built with [Hugo](https://gohugo.io/) and the [Ananke](https://github.com/theNewDynamic/gohugo-theme-ananke) theme, deployed to GitHub Pages.

## Prerequisites

- [Hugo](https://gohugo.io/installation/) (extended edition, v0.137.1+)
- Git

## Running locally

Clone the repo with submodules (the Ananke theme is a submodule):

```bash
git clone --recurse-submodules https://github.com/kimrs/kimrs.github.io.git
cd kimrs.github.io
```

If you already cloned without `--recurse-submodules`:

```bash
git submodule update --init --recursive
```

Start the dev server:

```bash
hugo server -D
```

The site will be available at `http://localhost:1313/`. Changes to content and templates hot-reload automatically.

## Creating a new post

```bash
hugo new posts/my-new-post/index.md
```

## Building for production

```bash
hugo --gc --minify
```

Output goes to `public/`.

## Deployment

Pushes to `master` trigger the GitHub Actions workflow (`.github/workflows/hugo.yaml`) which builds and deploys straight to production at **https://solstad.dev/** — the custom domain of this user site. There is no separate test deployment; preview locally with `hugo server` before pushing.

Because the domain sits on the user site, every other repo with Pages enabled publishes under `solstad.dev/<repo-name>/` (e.g. the talk decks).
