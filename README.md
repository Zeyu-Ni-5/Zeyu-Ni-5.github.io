# Zeyu Ni — Personal Website

An English portfolio with a compact dark layout, a short introduction, top-right LinkedIn/GitHub/resume/email links, and category buttons for projects, experience, education, awards, and skills. Built with HTML and CSS; no installation or build is required. Category selection works without JavaScript and supports keyboard arrow keys. Printing includes every category.

## Preview locally

Open `index.html` in a browser, or run from this folder:

```powershell
python -m http.server 4173 --bind 127.0.0.1
```

Then visit http://127.0.0.1:4173. Stop the server with Ctrl+C.

## Publish on GitHub Pages

1. Create a dedicated public repository under `Zeyu-Ni-5`. The recommended name is `Zeyu-Ni-5.github.io` if that repository is not already in use. This yields `https://zeyu-ni-5.github.io/`. Alternatively, use `personal-website`, which yields `https://zeyu-ni-5.github.io/personal-website/`.
2. Upload the contents of **this folder** to the root of that repository on branch `main`. Include `index.html`, `styles.css`, `assets/`, the original PDF, `.nojekyll`, and `.github/workflows/deploy.yml`. Do not upload the parent `Project` folder or sibling projects. The workflow file must be inside `.github/workflows/` in the repository, not nested under `Personal Website/`.
3. In the repository, open **Settings → Pages → Build and deployment → Source → GitHub Actions**.
4. Open **Actions → Deploy personal website to GitHub Pages → Run workflow**, selecting `main`. Later pushes to `main` deploy automatically.
5. Wait for the workflow to succeed; the `github-pages` deployment provides the actual published URL. A suggested URL is not proof of publication.

The workflow follows [GitHub's official custom workflow guidance](https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages). It stages only public site files, not `docs/`, temporary files, or unrelated projects. The existing PDF contains the contact details supplied in the resume and will be publicly accessible with the website.

If using Git locally in a new, empty remote repository:

```powershell
git init -b main
git add index.html styles.css assets 'Resume Zeyu Ni 2A.pdf' .nojekyll .github .gitignore README.md
git commit -m "feat: add personal portfolio website"
```

Add the exact remote URL copied from your new GitHub repository, then push `main`. Do not reuse the remote for a different project or overwrite an existing personal site.

## Update the website

- Personal information, project text, links: `index.html`.
- Colors, typography, spacing, mobile layout: `styles.css`.
- Favicon: `assets/favicon.svg`.
- Resume: replace `Resume Zeyu Ni 2A.pdf`, keeping the filename. If renamed, update all PDF links in `index.html` and the copy step in `.github/workflows/deploy.yml`.

The site uses relative asset URLs, so it supports both account-level and repository-level GitHub Pages. No analytics, external fonts, backend, or API keys are used. Browsers without CSS `:has()` support show all categories as a readable fallback.
