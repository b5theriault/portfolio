# Brandon Theriault — Portfolio Site

Quarto website with resume and work samples.
Live at: `https://[your-github-username].github.io/[repo-name]`

---

## First-time setup

### 1. Install Quarto (if not already)
```bash
brew install quarto
```

### 2. Create a GitHub repository
1. Go to [github.com/new](https://github.com/new)
2. Name it (e.g. `portfolio` — your site will live at `github.com/[username]/portfolio`)
3. Set visibility to **Public**
4. **Do not** initialise with a README — leave it empty

### 3. Initialise git and push source files
```bash
cd /Users/bmac/Projects/portfolio
git init
git add .
git commit -m "Initial portfolio commit"
git remote add origin https://github.com/boonding/[REPO-NAME].git
git branch -M main
git push -u origin main
```

### 4. Deploy to GitHub Pages
```bash
quarto publish gh-pages
```

Quarto builds the site, creates a `gh-pages` branch, and pushes the rendered HTML automatically. When prompted, confirm `Y`.

### 5. Enable GitHub Pages (if not automatic)
1. Go to your repo on GitHub
2. **Settings → Pages**
3. Source: **Deploy from branch** → `gh-pages` → `/ (root)`
4. Save

Your site will be live at `https://[your-username].github.io/[repo-name]` within a few minutes.

---

## Updating the site

After any edits to `.qmd` files or reports:

```bash
cd /Users/bmac/Projects/portfolio
quarto publish gh-pages
```

That's it — one command rebuilds and redeploys everything.

---

## Preview locally before publishing

```bash
cd /Users/bmac/Projects/portfolio
quarto preview
```

Opens a live-reloading preview at `http://localhost:XXXX`.

---

## Project structure

```
portfolio/
├── _quarto.yml          # Site config (nav, theme, footer)
├── index.qmd            # About / home page
├── resume.qmd           # Resume page
├── work-samples.qmd     # Work samples gallery
├── styles.css           # Custom CSS
├── reports/             # Self-contained HTML work sample reports
│   ├── ai-adoption-performance.html
│   ├── block-wide-activity-ml.html
│   ├── termination-deep-dive.html
│   ├── termination-executive.html
│   ├── h2-calibration.html
│   └── peopleops-dashboard.html
└── README.md
```

## Adding a new work sample

1. Render your R Markdown with `self_contained: true` in the YAML output options
2. Copy the HTML file into `reports/`
3. Add a card for it in `work-samples.qmd`
4. Run `quarto publish gh-pages`
