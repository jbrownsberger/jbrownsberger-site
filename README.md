# Joseph Brownsberger — Personal Site

A simple, static personal/academic website for Joseph Brownsberger (Philosophy PhD student / JD candidate,
University of Notre Dame). Built with plain HTML, CSS, and a touch of JS — no build step required.

## Structure

```
joseph-brownsberger-site/
├── index.html          # Home page: hero, about, research areas, contact
├── publications.html   # Publications, essays, and presentations
├── css/
│   └── style.css       # All styling (liquid-glass cards, color orbs, layout)
├── js/
│   └── main.js         # Small helper (footer year)
└── assets/
    ├── images/         # Put hero-landscape.jpg and headshot.jpg here
    └── Joseph-Brownsberger-CV.pdf   # Add your actual CV PDF here
```

## Before you deploy — 3 things to add

1. **Landscape photo**: Save an image as `assets/images/hero-landscape.jpg`, then in `css/style.css`
   find `.hero-bg-photo` and add:
   ```css
   background-image: url('assets/images/hero-landscape.jpg');
   ```
   (keep `background-size: cover; background-position: center;` — already set).

2. **Headshot**: Save your headshot as `assets/images/headshot.jpg`. In `index.html`, replace the
   `<div class="headshot-placeholder">...</div>` block with:
   ```html
   <img src="assets/images/headshot.jpg" alt="Joseph Brownsberger" style="width:100%;height:100%;object-fit:cover;border-radius:50%;">
   ```

3. **CV PDF**: Export your CV to PDF and save it as `assets/Joseph-Brownsberger-CV.pdf`
   (the links in both HTML files already point here — no other changes needed).

## Editing content

- **Bio / about text**: edit the `#about` section in `index.html`.
- **Research areas**: edit the four cards in the `#research` section in `index.html`.
- **Publications**: edit the lists in `publications.html` — organized into Peer Reviewed,
  Essays & Public Writing, and Presentations & Invited Lectures, matching your CV.
- **Colors**: all colors are CSS variables at the top of `css/style.css` under `:root`
  (`--accent-navy`, `--accent-gold`, `--accent-forest`). Change these to retheme the whole site.

## Deploying

### Option A — GitHub Pages (free, simplest)
1. Create a new GitHub repo (e.g. `joseph-brownsberger-site` or `<username>.github.io`).
2. Push these files to the repo root (or to `main` branch).
3. In the repo Settings → Pages, set source to the `main` branch, root folder.
4. Your site will be live at `https://<username>.github.io/<repo>/` (or the root domain if you
   named the repo `<username>.github.io`).

### Option B — Vercel
1. Push this folder to a GitHub repo.
2. In Vercel, "Add New Project" → import the repo. No framework/build settings needed
   (it's static HTML) — set the Framework Preset to "Other" and leave build command empty.
3. Deploy. Vercel will serve the files directly.

## Quick local preview

From inside the `joseph-brownsberger-site` folder, run:
```bash
python3 -m http.server 8000
```
Then open `http://localhost:8000` in your browser.
