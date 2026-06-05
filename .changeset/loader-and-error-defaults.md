---
'@_linked/css': minor
---

Default styling for `@_linked/react`'s built-in loader and error elements.

**New: `loader.css`.** Default `.ld-loader` styling — small SVG ring with `stroke-dasharray` animation, `stroke: currentColor` so it inherits the parent text color. Includes an opt-in `.ld-loader--infinity` variant used by `LinkedInfinityLoader` (a branded loader exported from `@_linked/react`).

**New: `error.css`.** Default `.ld-error` styling — small cross SVG using the new `--color-error` token.

**New: `--color-error` token.** Single semantic variable for failure states, mapped to Tailwind red. Apps override in their own `@theme { ... }` block.

**Auto-import.** Both `loader.css` and `error.css` are `@import`ed from `theme-defaults.css`, so any app already importing `@_linked/css/theme-defaults.css` picks them up without any extra setup. Apps override `.ld-loader` / `.ld-error` (size, color, animation) in their own theme.css to brand them.

No breaking changes.
