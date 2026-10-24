# Sprankel website — instructions for Claude

Static website (plain HTML + one CSS file, no build step, no JavaScript) for
Sprankel - Sarah Cammaert. Language of the site: Dutch.

## Rules

- **Edit the HTML files, not the CSS.** All styling is in `css/style.css`. Reuse the
  existing classes listed below. Do not read `css/style.css` unless a change truly
  needs a new style.
- **Never add `style="..."` attributes or `<style>` blocks** to HTML. If a new look
  is really needed, add a small class to the matching numbered section of
  `css/style.css` and tell the user.
- The header (logo + menu) and footer are **copied in every page**. A menu or
  footer change must be made in all `.html` files (use a search/replace over all).
- Links are relative: pages in a subfolder use `../` (e.g. `../css/style.css`,
  `../agenda.html`). Link to folder pages as `folder/index.html`.
- Images go in `assets/img/` (lowercase, dashes, no spaces). Prefer `.jpg`/`.webp`,
  max ~1400px wide.

## Files

```
index.html                         Home
over-sarah.html  agenda.html  contact.html  workshops-voor-vrouwen.html
gratis-inspiratie.html             (empty, also on the old site)
workshops-voor-ouder-kind-1/       index.html + het-wonderpad, knuffel-ontmoet, speel-verbind-1
aanbod/                            pages NOT in the menu (hidden on the old site too)
bedankt.html                       shown after the contact form is sent
404.html                           "page not found" (uses /root links on purpose)
css/style.css                      ALL styling (colours/fonts as variables at the top)
assets/img/  assets/icons/  assets/fonts/
```

## Page skeleton

```html
<main>
<section class="section [section--shaded|section--accent|section--image] [section--wave] [section--narrow]">
  <!-- only for section--image: --> <img class="section__bg" src="assets/img/x.jpg" alt="">
  <div class="container">
    ...content...
  </div>
</section>
</main>
```

- `section--shaded` beige background · `section--accent` orange background, white text ·
  `section--image` photo background with white text · `section--wave` wavy top/bottom edge ·
  `section--narrow` narrower text column.
- Home page top: `<section class="hero"><img class="hero__image" ...><div class="hero__content">...</div></section>`

## Content building blocks

| Want | HTML |
|---|---|
| Columns (stack on mobile) | `<div class="columns"><div class="col">…</div><div class="col">…</div></div>` |
| Unequal columns (parts of 12) | `<div class="col col-8">` + `<div class="col col-4">` |
| Image (fills column) | `<img class="img" src="assets/img/x.jpg" alt="…" loading="lazy">` |
| Smaller image | add `width="300"`; extra classes `center`, `right`, `round` |
| Button | `<p class="buttons [center]"><a class="btn" href="…">Tekst</a></p>` |
| Button variants | `btn btn--outline`, `btn btn--small` |
| Box | `<div class="box">…</div>` (thin border) / `box box--shaded` (beige) |
| Round icon | `<span class="icon icon--heart-shape-outline"></span>` (+ `icon--small`); others: `right-quotation-mark`, `user-shape`, `plant-leaf-with-white-details`, `branch-with-leaves-black-shape`, `certificate-shape`, `thumbs-up-hand-symbol` |
| Info table | `<table class="info-table"><tbody><tr><td>Prijs</td><td>€ 25</td></tr></tbody></table>` |
| Empty space | `<div class="space-xs|space-s|space-m|space-l"></div>` |
| Social media buttons | `<ul class="social">…</ul>` (copy from `index.html`) |
| Contact form | `<form class="contact-form" …>` (copy from `contact.html`) |

Text helpers: `center`, `right`, `bold`, `small`, `large`, `accent` (orange text),
`gray` (grey heading), `light`. Heading sizes: `xl`, `lg`, `sm`
(e.g. `<h1 class="xl accent">`). Headings are orange by default.

## Agenda (`agenda.html`)

Add a workshop by copying one `agenda-item` block, in date order:

```html
<div class="agenda-item">
  <div>
    <p class="agenda-item__date">Zondag 22 november</p>
    <p>🕙 10 – 11.30 u</p>
    <p>Speel &amp; Verbind · 5–7 jaar</p>
  </div>
  <a class="btn" href="https://forms.gle/..." target="_blank" rel="noopener">Schrijf in</a>
</div>
```

Remove items whose date has passed.

## Contact form

Sent through FormSubmit (formsubmit.co) to the address in the form's `action`.
The form exists in `index.html` and `contact.html`; keep both the same.
