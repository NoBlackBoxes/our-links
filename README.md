# No Black Boxes links

A small Markdown link page and newsletter signup page published with GitHub
Pages.

## Edit the links

Edit the list in `index.md`. GitHub Pages converts it to the website automatically.

## Add an event offer

1. Add the event to `_data/events.yml` with a unique identifier, message,
   discount and offer dates.
2. Build the site and test the event URL before creating or printing its QR
   code.

The GIF London QR uses:

<https://noblackboxes.github.io/our-links/signup/?event=gif-london-2026>

While the configured offer is active, that URL shows the GIF London message and
discount. Outside the offer window, the same URL shows the generic newsletter
signup page. The form remains available at all times.

The `event` query parameter is stored in the hidden Jotform field with the same
name. Jotform's submission time determines whether a signup arrived before the
deadline.

The date check only changes what the page displays. It does not securely enforce
the discount. Set the same deadline on the coupon or payment system and state
clearly what the discount applies to.

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
