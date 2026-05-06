# Skyframe — ENGR 103 Drone Presentation Site

Three styles of a multi-page website to present your RC drone with the 3D-printed chassis. Pick whichever one fits the vibe you want, then push it to GitHub and turn on Pages.

## What's in here

```
engr 103 project/
├── index.html              ← landing page that lets you preview all three styles
├── README.md               ← this file
├── site-dark/              ← Style 1: Modern dark / tech
│   ├── index.html          (Need)
│   ├── solution.html       (Solution + prototype specs)
│   ├── feedback.html       (User feedback + iterations)
│   ├── evidence.html       (Evidence the design works)
│   ├── gallery.html        (Photo gallery)
│   ├── styles.css
│   ├── assets/             (SVG illustrations — shared)
│   └── images/             (drop your photos here)
├── site-academic/          ← Style 2: Clean academic / engineering
│   └── (same 5 pages + assets)
└── site-bold/              ← Style 3: Bold / colorful
    └── (same 5 pages + assets)
```

## Step 1 — Preview locally in VS Code

1. Open the `engr 103 project` folder in VS Code.
2. Install the **Live Server** extension (by Ritwick Dey) if you don't have it.
3. Right-click `index.html` (the one in the project root) → **Open with Live Server**.
4. Click into each of the three styles to compare.
5. To preview a single style directly, right-click any `index.html` inside `site-dark/`, `site-academic/`, or `site-bold/` and choose Open with Live Server.

## Step 2 — Drop in your real photos

Each site has an `images/` folder. The HTML pages already reference these filenames:

- `printed-chassis-1.jpg` — front 3/4 hero shot of the chassis
- `printed-chassis-2.jpg` — top-down view
- `printed-chassis-3.jpg` — detail / close-up
- `print-in-progress.jpg` — chassis on the printer bed
- `drone-assembled.jpg` — fully assembled drone
- `flight-test.jpg` — flight or test photo

Save your real photos with these exact names into the `images/` folder of whichever site you pick (or all three). They'll automatically replace the placeholders.

If you only have one or two photos, no problem — the others will keep showing the friendly "📷" placeholder cards.

## Step 3 — Fill in your real content

Look for `[BRACKETS]` and `<span class="placeholder-tag">PLACEHOLDER</span>` markers in:

- **`feedback.html`** — Replace every quote with the real feedback you collected. Keep the structure (the design revisions reference each piece of feedback by number).
- **`solution.html`** — Verify the spec numbers (wheelbase, mass, infill %, etc.) match your actual print.
- **`evidence.html`** — Update with your real test results.

You can do this directly in VS Code — just open the file and edit the text.

## Step 4 — Push to GitHub

In the terminal, from inside the `engr 103 project` folder:

```bash
git init
git add .
git commit -m "Initial Skyframe site"
git branch -M main
```

Then create an empty repo on GitHub (no README, no .gitignore), copy the URL, and:

```bash
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

## Step 5 — Turn on GitHub Pages

1. Go to your repo on GitHub → **Settings** → **Pages** (in the sidebar).
2. Under **Source**, choose **Deploy from a branch**.
3. Branch: **main**, folder: **/ (root)**. Save.
4. Wait ~1 minute. Your site goes live at `https://<your-username>.github.io/<repo-name>/`.

That URL shows the landing page with all three styles. To link directly to one:
- `https://<your-username>.github.io/<repo-name>/site-dark/`
- `https://<your-username>.github.io/<repo-name>/site-academic/`
- `https://<your-username>.github.io/<repo-name>/site-bold/`

## Step 6 — (Optional) Use just one style as the main site

If you've decided on one style and don't want the picker, you can either:

**Option A — Keep all three but link straight to your favorite.**
Open `index.html` (the one in the project root) and change the line near the top so it redirects automatically. Add this inside `<head>`:
```html
<meta http-equiv="refresh" content="0; url=site-dark/index.html">
```
(Swap `site-dark` for whichever folder you picked.)

**Option B — Move your chosen style to the root.**
Delete the other two folders and the root `index.html`, then move the contents of (e.g.) `site-dark/` up into the project root.

## Editing tips

- All styling is in each site's `styles.css` — change colors there if you want.
- Page layouts use the same nav across pages, so to add a new page, copy any existing one and update the title + nav `class="active"` marker.
- The SVG illustrations in `assets/` are simple line drawings — you can edit them in any text editor or replace them with your own renders / Fusion 360 screenshots.

## Quick troubleshooting

- **Images don't show up after I added them:** Check the filename matches exactly (case-sensitive on GitHub Pages).
- **Layout looks broken on GitHub Pages but fine locally:** Make sure `styles.css` and the `assets/` and `images/` folders all got committed.
- **GitHub Pages shows 404:** Wait a couple of minutes after enabling — it can take up to ~5 min on the first deploy.

Good luck on the presentation!
