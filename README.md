# fin3133-investments-book

Public render/deploy repo for the **Investments** (FIN 3133) textbook.

The book source lives in the private repo
[`imrenhe/fin3133-investments`](https://github.com/imrenhe/fin3133-investments).
This repo's GitHub Action checks out that source, renders it with Quarto, and
publishes the result to GitHub Pages.

## How it works

1. A push to `main` in the private source repo fires a `repository_dispatch`
   (`source-updated`) at this repo.
2. [`.github/workflows/build.yml`](.github/workflows/build.yml) checks out this
   repo and the private source, renders with Quarto, and deploys `_book/` to
   GitHub Pages.

## Setup checklist

- [ ] Add a `BOOK_PUBLISH_TOKEN` secret (PAT with read access to the private source repo).
- [ ] Enable GitHub Pages with **GitHub Actions** as the source.
- [ ] Add a matching `BOOK_PUBLISH_TOKEN` secret in the private repo (for the trigger).
