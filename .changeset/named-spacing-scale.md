---
'@_linked/css': minor
---

Add a named spacing scale: `--space-2xs` through `--space-3xl`.

`--spacing()` is a compile-time function, so it needs the theme in scope. Any stylesheet
compiled on its own — a CSS module inside a package, a consumer's own sheet — fails with
"the --spacing theme variable was not found" and cannot use it at all. The workaround every
such package reaches for is a private spacing scale, which is precisely the fragmentation
`docs/styling-and-themes.md` warns against.

Naming the steps resolves them once, at theme build time, so `var(--space-md)` works
anywhere. The steps are the ones Create Now already uses, so this adopts a scale that is
load-bearing rather than proposing a new one. The `-plus` half-steps are kept rather than
rounded away: rounding them is what sends packages off to define their own scale.
