# Essays

Hugo blog using the [Fluidity](https://themes.gohugo.io/themes/hugo-theme-fluidity/) theme.
Live at https://dersavage.github.io/essays/.

- Essays: `content/posts/*.md` (front matter: `title`, `date`)
- All essays are listed on the home page at once (`params.pageSize.home` in `hugo.yaml`)
- Header menu: `menus.main` in `hugo.yaml`
- Requirements: Hugo **extended** >= 0.158 and Node.js (the theme compiles Tailwind CSS)
- First-time setup: `npm install`, then `hugo server`
- Deploys on every push to `main` via `.github/workflows/pages.yml`
- The theme is vendored in `themes/fluidity` with one fix for current Hugo versions:
  `templates.Defer` can no longer be used inside `partialCached`, so the stylesheet partial is called with `partial`.
  `hugo.yaml` also allows Hugo to run `node` and `tailwindcss` (`security.exec.allow`).
- Search is turned off (it needs Pagefind); comments and related posts are off too.
