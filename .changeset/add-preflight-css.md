---
'@_linked/css': patch
---

Add `preflight.css` to the package. A LINCD-flavored Tailwind preflight (with `:not()` exclusions to preserve legacy inline element styles) that consumers import via `@_linked/css/preflight.css`. Restores the asset that was missing locally and unblocks Create Now's `theme.css` / `ThemeShowcase.module.css` webpack/Tailwind builds.
