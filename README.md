# Sandpiper Portraits — Landing Page

A single-page landing site for a photography business built with HTML, CSS, and JavaScript. Processed by Jekyll on GitHub Pages (front matter only — no themes or plugins required). No external dependencies.

## Quick Start

Open `index.html` in any modern browser to preview locally. The Jekyll front matter (`---` block at the top) is ignored by browsers and only used during GitHub Pages deployment.

## Deploy to GitHub Pages

1. Create a new repository on GitHub (e.g. `sandpiperportraits-website`).
2. Push this project to the repository:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/sandpiperportraits-website.git
   git push -u origin main
   ```
3. Go to **Settings → Pages** in your repository.
4. Under **Source**, select the `main` branch and `/` (root) folder, then click **Save**.
5. GitHub Pages will run Jekyll automatically. Your site will be live at `https://YOUR_USERNAME.github.io/sandpiperportraits-website/` within a minute or two.

## Custom Domain Setup

1. Add a `CNAME` file to the repo root containing your domain on a single line:
   ```
   www.sandpiperportraits.com
   ```
2. With your DNS provider, add the following records:

   | Type  | Name  | Value                          |
   |-------|-------|--------------------------------|
   | A     | @     | 185.199.108.153                |
   | A     | @     | 185.199.109.153                |
   | A     | @     | 185.199.110.153                |
   | A     | @     | 185.199.111.153                |
   | CNAME | www   | YOUR_USERNAME.github.io        |

3. Back in **Settings → Pages**, enter your custom domain and check **Enforce HTTPS** once the DNS verification completes.

## Customizing Content

The HTML file uses `<!-- EDIT: -->` comments to mark every section you'll likely want to change. Search for `EDIT:` to find them all. Key areas:

| What to change                | Where to look                                                  |
|-------------------------------|----------------------------------------------------------------|
| Company name / brand          | `.nav-brand`, `.hero h1`, `.hero .section-label`               |
| Hero headline & tagline       | `.hero h1`, `.hero p`                                          |
| About section copy            | `#about .split-text`                                           |
| "What Makes Us Different"     | Second `.split` section — heading and body text                |
| Feature cards (The Experience)| `#experience .feature-card` — 4 cards                          |
| Services / What's Included    | `#services .include-item` — 6 items with icons                 |
| Testimonials                  | `#testimonials .testimonial-card` — 4 placeholder reviews      |
| FAQ questions & answers       | `#faq .faq-item` — 8 accordion items                           |
| Email address                 | `#contact` and footer — the `mailto:` links                    |
| Copyright line                | `.footer-bottom span`                                          |
| Photo placeholders            | `.split-image` divs — swap for `<img src="..." alt="...">` tags|

## Project Structure

```
.
├── _config.yml  # Jekyll configuration for GitHub Pages
├── CNAME        # Custom domain pointer
├── index.html   # Entire site (HTML + inline CSS + JS + Jekyll front matter)
└── README.md    # This file
```
