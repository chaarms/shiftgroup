# Sage Solutions LLC — Website

A modern, single-page site for Sage Solutions LLC, a government contracting startup offering procurement, staffing, consulting, IT support, and cybersecurity services.

## Structure

```
index.html          Main page (all sections)
assets/style.css     Styles (design tokens at top of file)
assets/script.js      Nav toggle, scroll reveals, contact form
```

## Deploying to GitHub Pages

1. Create a new repository (e.g. `sage-solutions-site`) and push these files to the `main` branch — keep `index.html` at the repo root.
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to `Deploy from a branch`.
4. Set **Branch** to `main` and folder to `/ (root)`, then **Save**.
5. GitHub gives you a URL like `https://<username>.github.io/sage-solutions-site/` within a minute or two.
6. Optional: add a `CNAME` file with your custom domain (e.g. `sagesolutionsllc.com`) if you buy one, and point its DNS at GitHub Pages.

## Things to replace before launch

Search the files for these placeholders:

- **Contact info** — `contact@sagesolutionsllc.com` and the phone number in `index.html` (Contact section and footer `mailto:`/`tel:` links).
- **SAM.gov / CAGE / NAICS / certifications** — the Trust Strip near the top, the "Engagement Status" panel, and the full Credentials section (`#capabilities`) all currently say "pending" / "TBD" / "on request." Update these the moment your registrations are live — agencies check this early.
- **Company address**, if you want one listed, in the Contact section.
- The favicon — none is set; add a `<link rel="icon">` once you have a mark, or keep the inline node-graph logo as-is.

## Notes on the contact form

GitHub Pages is static hosting with no backend, so the form currently opens the visitor's email client via a `mailto:` link pre-filled with their message. If you want real form submissions without a backend, swap the `fetch`/`mailto` logic in `assets/script.js` for a service like Formspree, Getform, or a Cloudflare Worker — the form markup is already set up to work with any of those with minimal changes.

## Editing content

Everything is in `index.html` — no build step or framework. Open it, change the copy, and refresh. The five service cards under `#services` map 1:1 to the nodes in the hero graph SVG if you ever add or rename a service line.
