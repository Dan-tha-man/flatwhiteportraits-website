# Sandpiper Portraits — Landing Page

A single-page landing site for a photography business built with plain HTML, CSS, and JavaScript. No frameworks, no build tools, no external dependencies.

## Quick Start

Open `index.html` in any modern browser — that's it.

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
5. Your site will be live at `https://YOUR_USERNAME.github.io/sandpiperportraits-website/` within a minute or two.

## Custom Domain Setup

1. In your repository, create a file named `CNAME` containing your domain on a single line:
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

| What to change              | Where to look                        |
|-----------------------------|--------------------------------------|
| Company name / brand        | `.nav-brand`, `.hero h1`             |
| Tagline                     | `.hero p`                            |
| About section copy          | `#about .about-text`                 |
| Service card titles & text  | `#services .service-card`            |
| Email address               | `#contact` — the `mailto:` links     |
| Copyright line              | `.footer span`                       |
| Photo placeholder           | `#about .about-image` — swap the div for an `<img>` tag |

## Project Structure

```
.
├── index.html   # Entire site (HTML + inline CSS + JS)
└── README.md    # This file
```
