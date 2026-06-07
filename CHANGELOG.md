# @\_linked/css

## 0.2.0

### Minor Changes

- [#3](https://github.com/linked-cm/css/pull/3) [`798c306`](https://github.com/linked-cm/css/commit/798c30615ed99b20cfa7d6f75ecfff362cb668e0) Thanks [@github-actions](https://github.com/apps/github-actions)! - `@_linked/css` 0.2.0 — package ready for consumption by Linked apps.

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

- [#4](https://github.com/linked-cm/css/pull/4) [`de38f84`](https://github.com/linked-cm/css/commit/de38f843400132f504b92bf59e13dd246868ec95) Thanks [@flyon](https://github.com/flyon)! - Default styling for `@_linked/react`'s built-in loader and error elements.

  **New: `loader.css`.** Default `.ld-loader` styling — small SVG ring with `stroke-dasharray` animation, `stroke: currentColor` so it inherits the parent text color. Includes an opt-in `.ld-loader--infinity` variant used by `LinkedInfinityLoader` (a branded loader exported from `@_linked/react`).

  **New: `error.css`.** Default `.ld-error` styling — small cross SVG using the new `--color-error` token.

  **New: `--color-error` token.** Single semantic variable for failure states, mapped to Tailwind red. Apps override in their own `@theme { ... }` block.

  **Auto-import.** Both `loader.css` and `error.css` are `@import`ed from `theme-defaults.css`, so any app already importing `@_linked/css/theme-defaults.css` picks them up without any extra setup. Apps override `.ld-loader` / `.ld-error` (size, color, animation) in their own theme.css to brand them.

  No breaking changes.

### Patch Changes

- [#3](https://github.com/linked-cm/css/pull/3) [`641b7c9`](https://github.com/linked-cm/css/commit/641b7c9a37656bfaf124234ba995842112131da2) Thanks [@github-actions](https://github.com/apps/github-actions)! - Remove `linkedPackage: true` — `@_linked/css` is a pure CSS asset package, not a JS module. The flag caused runtime consumers (like LincdServer's `getLincdPackages`) to attempt a dynamic `import()` of the package's main entry, which fails since there's no `index.js`.

## 0.1.1

### Patch Changes

- [`22e36e4`](https://github.com/linked-cm/css/commit/22e36e4a4e3ea05937284360e9b8e3af5ef8af94) - Initial release under the new publishing setup.
