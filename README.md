# zola-starter-gi

Minimal Zola site configured with GitHub Actions to deploy to GitHub Pages (gh-pages branch).

Getting started (local)
1. Install Zola: https://www.getzola.org/documentation/getting-started/installation/
2. Run locally:
   - zola serve   # local dev server at http://127.0.0.1:1111
   - zola build   # generates output in the directory configured by output_dir (public)

How CI deployment works
- On push to main, the workflow builds the site with Zola and uses peaceiris/actions-gh-pages to push the generated public/ content to the gh-pages branch.
- After the first successful run, the gh-pages branch will be created automatically.
- In your repository Settings -> Pages, set the Source to "gh-pages" branch and root folder (if not auto-selected).

Notes and customization
- base_url is set in config.toml to: https://Yamavu.github.io/zola-starter-gi — change it if you rename the repository or use a custom domain.
- To use a specific Zola version, edit the version field in .github/workflows/deploy.yml.
- To preserve a custom domain, add a CNAME file to the static/ directory or configure the peaceiris action with `cname`.
- Add more content under content/ and edit templates in templates/.

If you'd like, I can:
- add an example about page,
- change the Zola version used by the workflow,
- or create a theme/layout with navigation.