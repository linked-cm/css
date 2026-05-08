---
'@_linked/css': minor
---

`@_linked/css` 0.2.0 — package ready for consumption by Linked apps.

Breaking:
- Drop `variables.css` (legacy reference-token file from pre-Tailwind-v4 era; never wired into the new theme system; zero consumers).

Added:
- `tailwindcss: "^4"` declared as `peerDependencies`. The package's `theme-defaults.css` and `utilities.css` use Tailwind v4 directives (`@theme`, `@source inline()`, `@utility`, `--spacing()`); the requirement is now explicit.
- README documenting file structure, recommended import order, the two naming systems (state-first generic vs component-first specific), Tailwind v4 peer requirement, known gaps, and future ideas.
- `docs/styling-and-themes.md` moved in from the (retiring) `lincd` package.
- `preflight.css` moved in from `@_linked/cli`. Tailwind-derived preflight with `:not()` exclusions to preserve inline element styles (`<span>`, `<a>`, `<b>`, `<em>`, `<code>`, etc.). Apps that want LINCD-flavored CSS resets import this instead of the bundled Tailwind preflight; see README for the split-import pattern.

Cleanup:
- Fixed misleading comment in `utilities.css` (`mixins via @apply` → `Tailwind v4 @utility mixins`).

Part of master plan Phase 0.2.
