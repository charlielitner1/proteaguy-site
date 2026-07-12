# The Protea Guy — Website

A custom, editorial-style static website for **Ben Gill / The Protea Guy**.

The site is designed around a real Southern California farm story: site planning, propagation, soil and media work, planting, field development, grower education, and the farm’s current progress.

## What is included

- Responsive one-page website
- 23 optimized web images
- Mobile navigation
- Search and social sharing metadata
- Custom 404 page
- `CNAME` file for `proteaguy.com`
- `robots.txt` and `sitemap.xml`
- No database, login, plugins, form processor, trackers, or third-party scripts
- Direct email links to `proteaguy@gmail.com`

## Preview locally

The easiest option is to open `index.html` in a browser.

For a more accurate local preview, open Terminal in this folder and run:

```bash
python3 -m http.server 8000
```

Then visit:

```text
http://localhost:8000
```

## Site files

```text
index.html          Main website
styles.css          All design and responsive styling
script.js           Navigation and footer year
404.html            Custom not-found page
CNAME               Custom domain setting
robots.txt           Search crawler instructions
sitemap.xml          Search sitemap
assets/images/       Optimized website photography
assets/protea-mark.svg  Logo / favicon
```

## Updating text

Open `index.html` in any text editor. The visible copy is grouped into clearly labeled sections:

- Hero
- Meet Ben
- Farm story
- Expertise
- International experience
- Contact

## Replacing a photograph

1. Export the replacement as WebP or JPG.
2. Put it in `assets/images/`.
3. In `index.html`, find the old image filename and replace it.
4. Update the image `alt` description so it accurately describes the new photo.

## Security approach

This is a static site. There is no server-side code, database, WordPress installation, contact-form backend, account system, or payment collection. The email buttons use normal `mailto:` links.

A restrictive Content Security Policy is included in `index.html`. If third-party analytics, forms, fonts, or embeds are added later, that policy will need to be deliberately updated.

## Publishing

See **`LAUNCH-TONIGHT.md`** for the GitHub Pages and GoDaddy steps.
