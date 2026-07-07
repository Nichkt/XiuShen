# Notes for Later

A quiet, personal writing blog — notes written now, meant to be found later — built as a plain Jekyll site, hosted free on GitHub Pages.

## 1. Push it to GitHub

1. Create a new repo on GitHub. If you want it at `https://yourusername.github.io` directly, name the repo exactly `yourusername.github.io`. If you want it at `https://yourusername.github.io/some-name`, name it whatever you like — just set `baseurl: "/some-name"` in `_config.yml`.
2. From this folder:
   ```
   git init
   git add .
   git commit -m "Initial blog"
   git branch -M main
   git remote add origin https://github.com/yourusername/your-repo-name.git
   git push -u origin main
   ```

## 2. Turn on GitHub Pages

In the repo: **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: `main`, folder `/ (root)`**. Save. It builds in a minute or two, at the URL GitHub shows you there.

## 3. Fill in the config

Open `_config.yml` and set:
- `title`, `description`, `author`
- `url` — your GitHub Pages URL, e.g. `https://yourusername.github.io`
- `baseurl` — leave blank for a root `username.github.io` repo, or `/repo-name` otherwise

## 4. Write

Add a file to `_posts/` named `YYYY-MM-DD-a-slug.md`:

```
---
title: "Your Title"
subtitle: "Optional subtitle"
---
Body text in Markdown.
```

Commit and push. GitHub rebuilds the site automatically — no build step to run yourself.

## 5. (Optional) preview locally

Requires Ruby installed.

```
bundle install
bundle exec jekyll serve
```

Then visit `http://localhost:4000`.

## 5.5 (Optional) custom domain

Add a `CNAME` file at the repo root containing just your domain (e.g. `writing.yoursite.com`), then point a CNAME DNS record at `yourusername.github.io`. GitHub's Pages settings page will confirm once it's detected.

## Structure

- `_posts/` — every post, one file each
- `_layouts/` — page templates (`default`, `home`, `post`)
- `_includes/` — header/footer partials
- `assets/css/main.css` — all styling, no build step, plain CSS
- `about.md` — the About page; edit the bio text directly
- `index.md` — the home page (just sets the layout; posts render automatically)

## Design notes

Paper-grey background, near-black ink, a stamped vermillion "seal" mark next to each date — a quiet signature, like a mark of authenticity on a handwritten note. Newsreader for display type, Inter for UI text, IBM Plex Mono for dates. Posts get a drop cap on the first paragraph. Newest note always sits at the top of the list, seal filled in; older ones trail below with an outline seal.

RSS feed is automatic at `/feed.xml` via `jekyll-feed`, in case you ever want to read it somewhere other than the site itself.
