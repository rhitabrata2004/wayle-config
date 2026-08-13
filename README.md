# wayle config

[![wayle-media PR status](https://img.shields.io/github/pulls/detail/state/wayle-rs/wayle-services/44)](https://github.com/wayle-rs/wayle-services/pull/44)

Personal [wayle](https://github.com/wayle-rs/wayle) desktop shell config.

Uses a local `wayle-media` fork (see `~/wayle/Cargo.toml`'s `[patch.crates-io]`)
for a YouTube thumbnail fallback, [proposed upstream in PR #44](https://github.com/wayle-rs/wayle-services/pull/44).

- `config.toml` — bar layout, styling, and custom modules.
- `themes/*.toml` — palettes cycled by `bin/wayle-theme`.
- `bin/wayle-theme` — theme cycler bound to the `custom-theme-switcher` bar
  module's click actions. Tracked copy of `~/.local/bin/wayle-theme`; copy
  changes back manually (or symlink it) when editing.

## Themes

Left/right-click the theme switcher on the bar to cycle forward/back.
Each `themes/*.toml` is a flat `bg` / `surface` / `elevated` / `fg` /
`fg_muted` / `primary` / `red` / `yellow` / `green` / `blue` palette; adding
a file adds it to the rotation, no config changes needed.

Each theme also has a matching wallpaper at `themes/wallpapers/<name>.jpg`
(a subtle diagonal `bg` → `elevated` gradient with a soft `primary`-colored
glow, generated from the theme's own palette) applied via `wayle wallpaper
set` alongside the color switch. A theme with no matching wallpaper file
just skips this step. Requires wayle's own `awww` wallpaper engine to own
the wallpaper layer — see the note below.

- Catppuccin Mocha
- Catppuccin Macchiato
- Tokyo Night
- Dracula
- Nord
- Gruvbox Dark
- Everforest
- One Dark
- Rosé Pine
- Kanagawa
- Solarized Dark
- Cyberpunk *(no single canonical spec — built as a cohesive neon-on-dark-purple palette)*

## Wallpaper engine note

`hyprpaper` and wayle's own `awww` engine both try to render the wallpaper
layer; having both running silently breaks wallpaper switching (the `wayle
wallpaper set` call succeeds but nothing changes on screen since hyprpaper
already owns the layer). `~/.config/hypr/modules/autostart.lua`'s
persistent `hyprpaper` autostart is disabled for this reason — video
wallpapers still get it started on-demand via `restore-wallpaper.sh`
(which also kills it again for image wallpapers), so that path is
unaffected.
