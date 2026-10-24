# Sprankel - Sarah Cammaert — website

Static rebuild of https://www.sprankel-sarah-cammaert.be (previously hosted on JouwWeb).
Plain HTML + one stylesheet (`css/style.css`), no build step.

## Preview locally

Open `index.html` in a browser, or run a small server so links behave like online:

```
python3 -m http.server 8000
```

and go to http://localhost:8000.

## Hosting

Upload the whole folder to any static host, e.g. Netlify, Cloudflare Pages or
GitHub Pages (all free), or any regular web hosting via FTP. Then point the domain
`sprankel-sarah-cammaert.be` to it.

The old addresses (like `/over-sarah` or `/workshops-voor-ouder-kind-1/het-wonderpad`)
keep working on Netlify, Cloudflare Pages and GitHub Pages, because they serve
`over-sarah.html` for `/over-sarah` automatically.

## Contact form

The form uses [FormSubmit](https://formsubmit.co) (free, no account).
**The first time someone sends the form, FormSubmit e-mails an activation link to
sarahcammaert@gmail.com — click it once**, after that messages arrive normally.
After sending, visitors land on `bedankt.html`.

## Editing with Claude

See `CLAUDE.md`: Claude edits the HTML pages and reuses the classes from
`css/style.css`, so the stylesheet rarely needs to be read or changed.
