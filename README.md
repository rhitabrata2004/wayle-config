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
