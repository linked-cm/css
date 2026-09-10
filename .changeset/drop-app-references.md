---
'@_linked/css': patch
---

Stop naming a specific application in the theme.

A framework package should not name one of its consumers — a reader of the token
documentation has no way to know what that application is, and it implies the tokens exist
to serve it rather than the other way round. The spacing-scale comment and one line of the
styling guide are reworded to describe the tokens on their own terms.
