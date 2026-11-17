# Tonk Docs

Public documentation for Tonk, built with [mdBook](https://rust-lang.github.io/mdBook/) and published to GitHub Pages on every push to `main`.

## Edit

Pages live in `src/`. Add a page by creating the file and listing it in `src/SUMMARY.md`.

## Preview locally

```sh
cargo install mdbook --version 0.5.4 --locked
mdbook serve --open
```

## Publishing

`.github/workflows/deploy.yml` builds the book and deploys it with GitHub Pages. In the repo's Settings > Pages, set Source to **GitHub Actions**.

For a custom domain, set it in Settings > Pages and change `site-url` in `book.toml` to `"/"`.
