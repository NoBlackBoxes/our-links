# No Black Boxes links

A small Markdown link page and separate event signup pages published with
GitHub Pages.

## Edit the links

Edit the list in `index.md`. GitHub Pages converts it to the website automatically.

## Add an event signup page

1. Copy `events/_template.md` to `events/event-name.md`.
2. Replace every placeholder in its frontmatter:
   - `permalink` is the address encoded in the event QR code.
   - `event` is stored in the hidden Jotform field.
   - `offer_starts` is the machine-readable start, including its time zone.
   - `offer_ends` is the machine-readable deadline, including its time zone.
   - `offer_ends_label` is the same deadline written for visitors.
   - `jotform_id` is the ID of the permanent signup form.
3. Replace the final line with the permanent, event-specific message.
4. Build the site and test the event URL before creating or printing its QR code.

For example, a permalink of `/events/example-2026/` produces:

<https://noblackboxes.github.io/our-links/events/example-2026/>

The event name, event message and form remain on the page permanently. The
discount box is shown only between `offer_starts` and `offer_ends`. Keep the
page at the same address because printed QR codes cannot be changed.

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
