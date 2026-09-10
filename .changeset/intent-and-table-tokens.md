---
'@_linked/css': minor
---

Adds two token families the theme was missing, both because a consuming package had to
invent them locally — which is the fragmentation `docs/styling-and-themes.md` warns against.

**`--intent-{danger,success,warning,info}-{bg,bg-subtle,border,icon,text}`** — severity, for
any component that needs it. This is the axis `--notification-*` cannot express: those
tokens describe a container (padding, radius, shadow, one accent), not how serious the thing
inside it is. Kept separate rather than folded in, because a form field showing a validation
error is not a notification but it is `danger`. `-bg` is a solid tint; `-bg-subtle` is
transparent so it composes over whatever is behind it; `-icon` is a step stronger than
`-text` because an icon carries less area and needs more contrast to read at the same
weight.

**`--table-{header-bg,header-text,header-border,row-bg,row-bg-hover,row-border,cell-text,cell-text-primary}`**
— the one composite component family the set was missing, alongside `--list-item-*`,
`--modal-*`, `--navigation-*` and `--selector-*`. A list has no header row and no
cell/row distinction, so a table cannot borrow `--list-item-*`. Two text tokens on purpose:
`--table-cell-text` is the default cell weight and `--table-cell-text-primary` is the
identifying column, which wants more contrast because it is what a reader scans down.
