# Personal Academic Website

Plain static HTML/CSS site. No build step.

## Local preview

```bash
node serve.mjs
# open http://localhost:3000
```

## Editing content

Everything lives in `index.html`. Search for `[placeholder` / `[Last Name]` / `#` to find all fields to replace:

- **Name** — `Simone [Last Name]` (top of `index.html`, nav, footer)
- **Affiliation / tagline** — in the `.intro` block
- **Contact links** — in `.contact` list (email, scholar, github, linkedin)
- **About** — three `<p>` tags in `#about`
- **Papers** — two `<article class="paper">` blocks in `#research`:
  - Title (`<h3>`), status, abstract
  - Links in `.paper-links` (set real URLs)
- **Photo** — replace `.headshot` `src` with `assets/photo.jpg`
- **CV** — put PDF at `assets/cv.pdf`

## Styling

Single stylesheet: `style.css`. Tokens at the top (`:root`) control all colors, fonts, spacing. Palette is intentionally restrained:

- `--accent: #7a1f1f` — muted deep red for links. Change once, propagates everywhere.
- Body font: EB Garamond (serif). UI font: Inter.

## Deploying to GitHub Pages

1. Create a GitHub repo named `<your-username>.github.io` (exact name — required for a user site).
2. From this folder:

   ```bash
   git init
   git add .
   git commit -m "Initial site"
   git branch -M main
   git remote add origin git@github.com:<your-username>/<your-username>.github.io.git
   git push -u origin main
   ```

3. On GitHub: Settings → Pages → Source = `main` / root. Site goes live at `https://<your-username>.github.io` in a few minutes.
4. Custom domain (optional): add a `CNAME` file with your domain, then point DNS to GitHub's IPs.

## Files

| File | Purpose |
|---|---|
| `index.html` | Entire page content |
| `style.css` | All styling |
| `serve.mjs` | Tiny local dev server (Node, no deps) |
| `assets/` | Photo, banner image, CV PDF (add your own) |
