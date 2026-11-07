# Essays

Hugo blog using the [Hugolify](https://themes.gohugo.io/themes/hugolify-theme/) theme
(starter template + `hugolify-theme-design-system` styling module).
Live at https://dersavage.github.io/essays/ once GitHub Pages is switched to "GitHub Actions".

- Essays: `content/posts/*.md` (front matter: `title`, `date`)
- Header menu: `data/menu/header/primary.yml`; site name and description: `data/seo.yml`
- Requirements: Hugo **extended** >= 0.158, Go, Node.js
- First-time setup: `hugo mod get && hugo mod npm pack && npm install`, then `hugo server`
- Deploys on every push to `main` via `.github/workflows/pages.yml`
- The Hugolify admin/CMS module was removed from `config/_default/module.yaml`, so no `/admin` page is published.
