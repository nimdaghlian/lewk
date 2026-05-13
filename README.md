# lewk

A minimal editorial CSS framework. One foreground + one background + one accent per theme; every other token derives via `color-mix()` and alpha. Hairline rules instead of cards. Instant theme + font swapping.

Open `index.html` in a browser to see the full demo. Click the swatches in the bottom-right to switch themes; right-click anywhere on the switcher to roll a random pairing.

## Files

- `lewk.css` — the framework (tokens, layouts, components)
- `themer.js` — the theme + font switcher (optional)
- `index.html` — the demo page and shell template

## Use it

1. Copy `lewk.css` into your project.
2. Copy the `<head>` and `<body>` shell from `index.html` into your base layout. Keep the `<html data-theme="light" data-font="serif">` root and the Google Fonts `<link>`.
3. Copy `themer.js` if you want the live theme/font switcher; otherwise pick a fixed theme by setting `data-theme` on `<html>`.
4. Replace the demo content with your own.

For site-specific patterns that lewk doesn't ship (wiki backlinks, custom web components, project-specific badges), add a second stylesheet loaded after `lewk.css` so it can reference its tokens.

## Token system

Themes override only three variables:

```css
[data-theme="light"] { --fg: #111; --bg: #fff; --accent: #d31138; }
```

Six alpha-stepped swatches, buffer tints, hairline rules, and muted text all derive from those three. New themes must pass WCAG AA (4.5:1 contrast on `--fg` vs `--bg`).

## Built-in themes

`light`, `paper`, `dark`, `noir`, `ocean`, `moss`, `hot`, `lagoon`, `iris`, `lemon`, `blueprint`, `rose`, `newsprint`.

## Built-in fonts

`serif` (Lora), `sans` (Inter), `block` (Space Grotesk), `mono` (system), `pixel` (VT323).

## Primitives

| Class | Use |
|-------|-----|
| `.page` | Full-bleed page container |
| `.section` | Hairline-ruled section |
| `.row` | Label / content two-column row |
| `.dir` | Three-column directory listing |
| `.split` | Sidebar + main, with `--even` / `--wide` / `--thin` |
| `.cols-2/3/4` | Fixed N-column grid, responsive |
| `.grid` | Auto-fill responsive grid |
| `.rails-2/3/4` | Equal-weight columns with vertical hairlines |
| `.feature` | Magazine-style image+text split |
| `.hero` | Full-bleed featured block |
| `.prose` | Article body width container |
| `.stack` / `.cluster` | Vertical / horizontal flow utilities |

## Components

`.nav`, `.colophon`, `.footer`, `.card`, `.btn`, `.block`, `.tag`, `.cloud`, `.filter-bar`, `.status`, `.themer`.

## Design conventions

- Hairlines only (no thick borders, no `box-shadow` chrome).
- No `border-radius` on layout containers.
- Equal-weight columns instead of grayed-out sidebars.
- Text labels in nav (no icon-only).
- New themes pass WCAG AA.

## License

MIT
