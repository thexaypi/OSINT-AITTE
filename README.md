# OSINT AITTE — corporate intelligence website

Static, framework-free site (HTML, CSS, vanilla JS) built for GitHub Pages.
No cookies, no analytics, no third-party requests: fonts are self-hosted.

## Deploy to GitHub Pages
1. Push the contents of this folder to the root of a repository.
2. Settings → Pages → Source: "Deploy from a branch", branch `main`, folder `/ (root)`.
3. All internal links are relative, so the site works at `username.github.io/repo/` and on a custom domain.
4. `.nojekyll` is included so every folder is served as-is.
5. `404.html` resolves links automatically on project pages. On a user site or custom domain with
   nested broken URLs, add `<script>window.SITE_BASE='/'</script>` before the base script in `404.html`.

## Structure
- `index.html`, `services.html` — home and the numbered service catalogue
- `services/*.html` — ten service pages, each with the fourteen required sections
- `methodology.html` — ten-stage Intelligence Methodology Framework (separate from the services)
- `about.html`, `engagement-process.html`, `faq.html`, `contact.html`
- `privacy-policy.html`, `terms-gdpr.html`, `ethical-commitment.html`, `intellectual-property.html`
- `assets/` — CSS, JS, fonts (OFL licences included), favicon
- `_build/` — Python generator. Edit content there, then run `python3 _build/build.py`.

## Editing content
- Service content lives in `_build/services_data.py`. The script asserts that the ten official titles
  and their order are unchanged; the build fails if they drift.
- Business details (email, KVK number, address) live in `CONFIG` in `_build/layout.py`.

## Before launch — required
- Replace `[KVK number to be added]` and `[Registered business address to be added]` in `CONFIG`
  (a KVK number on the website is a Dutch legal requirement for registered businesses).
- Confirm the enquiry mailbox in `CONFIG["email"]` exists.
- Have the Privacy Policy and Terms reviewed by a Dutch lawyer. They are carefully drafted but are not legal advice.
- Confirm your position under the Wpbr (licensing for investigation activities) with counsel.
- Click through every link under "Relevant Official Resources" once; official sites occasionally restructure.
