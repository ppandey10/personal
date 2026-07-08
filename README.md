# Personal Website

Personal website of [Prasoon Pandey](https://ppandey10.github.io/personal/), built with [Hugo](https://gohugo.io/).

## Local development

```bash
cd site
hugo server
```

## Deploy

The site is deployed automatically to GitHub Pages on pushes to `main` via the Hugo workflow in `.github/workflows/hugo.yaml`.

In the GitHub repository settings, set **Pages → Build and deployment → Source** to **GitHub Actions** (not "Deploy from a branch"). That stops GitHub's default Jekyll build from running on every push.
