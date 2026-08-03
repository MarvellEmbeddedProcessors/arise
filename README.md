# ARISE — HiPC 2026 Tutorial Website

**ARISE: AI Research through Infrastructure Simulation and Evaluation**

A static, single-page website for the ARISE half-day tutorial proposed for HiPC 2026. The site presents the
tutorial abstract, objectives, topics, schedule, and presenter biographies, and will host slides, hands-on lab
guides, software setup instructions, and reference materials upon acceptance.

Content is sourced from [`README.txt`](README.txt) (the original tutorial proposal text).

## Structure

```
.
├── index.html          # Single-page site (all sections)
├── css/
│   └── style.css       # Styling (dark theme, responsive layout)
├── js/
│   └── main.js         # Mobile nav toggle, active-section highlighting
├── .nojekyll           # Tells GitHub Pages to skip Jekyll processing
└── README.txt          # Original tutorial proposal source content
```

No build step or dependencies are required — it's plain HTML/CSS/JS.

## Local preview

From this directory, run a simple local server and open the printed URL in your browser:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

(Opening `index.html` directly in a browser also works, but a local server is closer to production.)

## Deploying with GitHub Pages

1. Create a new GitHub repository (or use an existing one) and push this directory's contents to it:

   ```bash
   git init
   git add .
   git commit -m "Add ARISE tutorial website"
   git branch -M main
   git remote add origin <your-repo-url>
   git push -u origin main
   ```

2. On GitHub, go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to `Deploy from a branch`.
4. Choose the `main` branch and the `/ (root)` folder, then **Save**.
5. GitHub will publish the site at `https://<username>.github.io/<repo-name>/` (or `https://<username>.github.io/`
   if the repo is named `<username>.github.io`).

## Updating content

- Schedule, topics, and bios live directly in [`index.html`](index.html) — edit the relevant `<section>` blocks.
- Once slides, lab guides, setup instructions, and references are ready, replace the "Coming soon" badges in the
  **Resources** section with links to the actual files (e.g. hosted PDFs, a `slides/` folder, or external links).
- Presenter photos can replace the initials avatars by swapping the `.avatar` `<div>` for an `<img>` tag in the
  **Presenters** section.
