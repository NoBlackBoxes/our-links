# No Black Boxes links

A small Markdown link page published with GitHub Pages.

## Edit the links

Edit the list in `index.md`. GitHub Pages converts it to the website automatically.

## Local development

1. Install the Ruby gems locally to avoid permission issues:

   ```bash
   bundle config set --local path vendor/bundle
   bundle install
   ```

2. Serve the site locally:

   ```bash
   bundle exec jekyll serve
   ```

3. Visit <http://127.0.0.1:4000/our-links/>.

Notes:

- `_site/`, `.jekyll-cache/`, `.bundle/` and `vendor/` are generated locally
  and ignored by Git.
- Restart the server after changing `_config.yml`.

## Publish

1. Push `main` to GitHub.
2. In **Settings → Pages**, select **Deploy from a branch**.
3. Select the `main` branch and `/ (root)`, then save.

The site and QR code use this address:

<https://noblackboxes.github.io/our-links/>
