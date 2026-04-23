---
'@_linked/css': patch
---

Remove `linkedPackage: true` — `@_linked/css` is a pure CSS asset package, not a JS module. The flag caused runtime consumers (like LincdServer's `getLincdPackages`) to attempt a dynamic `import()` of the package's main entry, which fails since there's no `index.js`.
