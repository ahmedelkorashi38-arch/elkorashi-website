# ELKORASHI — Production Deployment Package

Production-ready static website for ELKORASHI (WPC Doors Manufacturing).

## What's inside

- `index.html` — the complete website (single self-contained file: all CSS, JS, fonts and images are inlined, so it works fully offline with zero build step).
- `assets/` — original source images (logo, favicon) kept for reference/editing.
- `favicon.png` — site icon (also referenced inside `index.html`).
- `assets/downloads/ELKORASHI-Catalog.pdf` — the official catalog, linked with `#page=N` deep links matching each finish code (see mapping below) from the product detail modal, and offered as a plain full download from the nav, Colors & Finishes banner, footer, and each product modal.
- `assets/colors/A01.jpg` … `A010.jpg` — the 10 official door finish photos (optimized JPEGs, ~30–85KB each), shown in the Colors & Finishes grid and in the click-to-open product detail modal (with image zoom).
- `robots.txt` — basic SEO crawler rules.

## Catalog page mapping

Each finish code deep-links to its page in the catalog PDF via "View in Catalog":

A01→8, A02→9, A03→10, A04→11, A05→12, A06→5, A07→13, A08→14, A09→15, A010→16.

If you replace the PDF later, update these page numbers in `ELKORASHI.dc.html`'s logic (`PAGE_MAP`) to match the new layout.

No `package.json`, build tools, or server code are required — this is a static site.

## Deploy to GitHub

1. Go to github.com → **New repository** (e.g. `elkorashi-website`).
2. On the new repo page, use **"uploading an existing file"** (or `git init` + `git add .` + `git commit` + `git push` if you use the command line) and upload everything in this folder.
3. Commit to the `main` branch.

## Deploy to Vercel

1. Go to vercel.com and sign in (GitHub login works directly).
2. **Add New… → Project**.
3. Import the GitHub repository you just created.
4. Framework Preset: **Other** (static site — no build command, no output directory needed).
5. Click **Deploy**. Vercel will give you a live `.vercel.app` URL within about a minute.
6. Optional: in Project → Settings → Domains, attach your own domain (e.g. `elkorashi.com`).

## Before going live — replace these placeholders

Edit directly in the page (or open `index.html` in a text editor and search for the text):

- Phone number: currently `+20 100 000 0000`
- Email: currently `info@elkorashi.com`
- Factory address: currently "Add factory address here" / "أضف عنوان المصنع هنا"
- Social links in the footer (Facebook / LinkedIn / Instagram) currently point to placeholder URLs
- Hero, About, Products, Manufacturing and Contact page images are drag-and-drop placeholders — replace them with real factory/product photography for the strongest result.

## Notes

- The Request-a-Quote form uses a `mailto:` link — clicking Send opens the visitor's email app addressed to the Email above with their info pre-filled. For fully automatic backend form delivery (e.g. into a Microsoft 365 inbox without opening a mail app), wire the form to a service like Power Automate, Formspree, or similar and swap the `mailto:` href for that endpoint.
- The site includes an Arabic/English toggle (RTL/LTR) in the top navigation.
