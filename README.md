# SurgTAP-3D project page

A standalone static export of the updated SurgTAP-3D project page. It includes the teaser, full abstract, dataset statistics, pipeline and analysis figures, tracking examples, synchronized tracker comparisons, application videos, and the manuscript PDF.

## Run locally

1. Extract the ZIP.
2. Open a terminal in the extracted `SurgTAP-3D` folder.
3. Run:

   ```bash
   python3 run.py
   ```

   On Windows, use `py run.py` if `python3` is unavailable.
4. Open **http://localhost:8000/**.
5. Press **Ctrl+C** in the terminal to stop the server.

For a different port, use `python3 run.py --port 8080` and open http://localhost:8080/.

The included server uses only Python's standard library and supports video byte-range requests, so video seeking and chapter navigation work locally. No npm installation, build, API key, or account sign-in is needed. You can also open `index.html` directly for a quick look; the local server is preferable for video playback.

## Publish on GitHub Pages

1. Create a GitHub repository, for example `surgtap-3d`.
2. Put the **contents** of the extracted `SurgTAP-3D` folder at the repository root. `index.html`, `styles.css`, `script.js`, `assets/`, and `.nojekyll` should sit directly in that root. Upload the extracted files, rather than the ZIP itself.
3. Commit and push the files to your `main` branch. Using Git also includes the hidden `.nojekyll` file:

   ```bash
   git init -b main
   git add .
   git commit -m "Add SurgTAP-3D project page"
   git remote add origin https://github.com/YOUR_USERNAME/surgtap-3d.git
   git push -u origin main
   ```

   Replace `YOUR_USERNAME` and the repository name with your own values. If you cloned an existing repository, copy the files into that checkout and commit/push normally.
4. In the repository, open **Settings → Pages**.
5. Under **Build and deployment**, choose **Deploy from a branch**. Select **main** and **/(root)**, then click **Save**.
6. When deployment completes, your project URL will be:

   ```text
   https://YOUR_USERNAME.github.io/surgtap-3d/
   ```

For a user/organization site, use a repository named `YOUR_USERNAME.github.io`; its URL will be `https://YOUR_USERNAME.github.io/`.

All local assets use relative paths, so the page works both at a domain root and under a GitHub project subdirectory. The `.nojekyll` file disables Jekyll processing. No custom domain, configuration file, or custom GitHub Actions workflow is required for the branch-based route above.

Official GitHub instructions:
- https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
- https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site

## Files to edit

| File | Purpose |
| --- | --- |
| `index.html` | Title, abstract, sections, resource links, and figure/video captions |
| `styles.css` | Colors, typography, spacing, and responsive layout |
| `script.js` | Action examples, source counts, benchmark values, and video controls |
| `assets/` | All figures, videos, posters, favicon, and manuscript PDF |
| `.nojekyll` | GitHub Pages static-site marker; retain this file |
| `run.py` | Optional local server; GitHub Pages does not execute it |

### HTML section map

`index.html` is kept as one static file so it still works when opened directly. Its major page modules are expanded, consistently indented, and labeled with `<!-- Module: ... -->` comments.

| Module | Section ID or marker |
| --- | --- |
| Header and navigation | `<!-- Module: Site header... -->` |
| Hero and headline statistics | `.hero` and `.stats` |
| Abstract | `#overview` |
| Dataset | `#dataset` |
| Tracking demos | `#explore` |
| Project video | `#project-video` |
| Annotation method | `#method` |
| Tracker comparisons | `#comparisons` |
| Benchmark results | `#benchmark` |
| Applications | `#applications` |
| Resources and FAQ | `#resources` |

Search for a section ID or `Module:` in the editor to jump directly to the area you want to revise.

Author details and dataset/code release links are left unset in this export, matching the supplied anonymous manuscript. Add those details in `index.html` when ready.

The media and PDF are bundled locally. Google Fonts is the only optional external visual dependency; if unavailable or offline, the page uses its built-in system-font fallbacks. To remove that dependency, delete the first `@import` line in `styles.css`.

No Sites-specific hosting manifest, authentication code, credentials, or Git history is included.

## Design update

The theme follows the figures: pale blue, warm cream, and peach, with blue controls and neutral text. Repeated summaries are removed, while supplementary visualizations and the full presentation can be expanded on demand.
