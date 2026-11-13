# No Black Boxes links

A small Markdown link page and newsletter signup page published with GitHub
Pages.

## Edit the links

Edit the list in `index.md`. GitHub Pages converts it to the website automatically.

## Add an event offer

1. Add the event to `_data/events.yml` with a unique identifier, message,
   discount and offer dates. For example:

   ```yml
   example-event-2027:
     name: Example Event 2027
     message: Add the event-specific message here.
     discount: 5%
     discount_applies_to: all No Black Boxes courses
     offer_starts: "2027-03-10T00:00:00Z"
     offer_ends: "2027-03-17T00:00:00Z"
     offer_ends_label: 17 March 2027 at 00:00 GMT
   ```

2. Build the site and test the signup page before the event begins.
3. Commit and push the new configuration:

   ```bash
   git add _data/events.yml
   git commit -m "Add Example Event offer"
   git push
   ```

The single QR code always uses:

<https://noblackboxes.github.io/our-links/signup/>

When an event is active, that page automatically shows its configured message
and discount. Outside an event window, it shows the generic newsletter signup
message. The form remains available at all times.

Do not create a new page, QR code or Jotform for each event. Every event uses
the same signup page, QR code and permanent Jotform.

During an event, the page adds the event identifier to its own URL so Jotform
can store it in a hidden Short Text field. Its Jotform Unique Name must be
exactly `event`; leave its default value empty and do not make it required.
Jotform's submission time determines whether a signup arrived before the
deadline. Do not configure overlapping event windows.

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

## QR code assets

- `assets/links-qr-code.svg` points to the general links page:
  <https://noblackboxes.github.io/our-links/>
- `assets/signup-qr-code.svg` points to the permanent newsletter and event
  signup page: <https://noblackboxes.github.io/our-links/signup/>

The signup QR code does not change between events. Test both saved files with a
phone before printing them.
