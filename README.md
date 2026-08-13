# The Guy Auto Detailing — Website

A single-file, no-build website. Everything (HTML, CSS, JS) lives in `index.html`,
so there's nothing to install and nothing to compile — open it and go.

## Opening it in Visual Studio Code

1. Unzip / save this folder anywhere on your computer.
2. Open the folder in VS Code (`File > Open Folder`).
3. Install the **Live Server** extension (search it in the Extensions panel).
4. Right-click `index.html` → **Open with Live Server**.
5. The site opens in your browser and refreshes automatically every time you save a change.

You don't need Node, npm, or any build tool. It's plain HTML/CSS/JS.

## The things you'll want to edit first

All of these are near the top of the file, clearly marked:

| What | Where |
|---|---|
| WhatsApp number & display phone | Bottom of `index.html`, in the `CONFIG` block inside the `<script>` tag |
| Colours (royal blue / green / background) | Top of `index.html`, in the `:root { ... }` CSS variables block |
| Before/after gallery photos | The `<div class="compare-after">` / `<div class="compare-before">` blocks in the Gallery section — replace with `<img src="images/your-photo.jpg">` |
| Reviews text | The `.review-card` blocks in the Reviews section |
| Google Reviews link | Search for `google.com/search?q=The+Guy+Auto+Detailing` and swap in your actual Google Business review link |
| Service descriptions / pricing tiers | The `.service-card` blocks in the Services section |
| Address / hours | The `.contact-line` entries in the Booking section |

## How the WhatsApp booking works

The booking form and every "Chat on WhatsApp" button build a `wa.me` link with
the visitor's details pre-filled, then open it in a new tab. No backend, no
database, no email server needed — it hands off straight to WhatsApp.

To set your number: open `index.html`, find `const CONFIG = {` near the bottom,
and set `whatsappNumber` to your number in international format with no `+`
and no spaces or leading zero — e.g. a South African number `082 123 4567`
becomes `27821234567`.

## Adding real before/after photos

Create an `images/` folder next to `index.html`, drop your photos in, then in
the Gallery section replace a placeholder block like:

```html
<div class="compare-layer compare-after">
  <span class="compare-label">AFTER</span>
</div>
```

with:

```html
<img src="images/car1-after.jpg" style="position:absolute; inset:0; width:100%; height:100%; object-fit:cover;">
```

Do the same for the matching `compare-before` block. The drag-slider JavaScript
doesn't need any changes — it works on whatever is inside those two layers.

## Deploying it live

This is a static site, so any of these work with no configuration:
- **Netlify** or **Vercel** — drag the folder onto their dashboard
- **GitHub Pages** — push the folder to a repo and turn on Pages in settings
- Any regular web host — just upload `index.html` (and an `images/` folder if you add one)

## Working on this with Claude going forward

Paste sections of `index.html` back into a chat with Claude any time you want
to add a page, change the layout, add a new service, or restyle something —
the whole site is plain, readable HTML/CSS/JS, so it's easy to hand edits back
and forth.
