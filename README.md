# wayle config

Personal [wayle](https://github.com/wayle-rs/wayle) desktop shell config.

- `config.toml` — bar layout, styling, and custom modules.
- `themes/*.toml` — palettes cycled by `bin/wayle-theme`.
- `bin/wayle-theme` — theme cycler bound to the `custom-theme-switcher` bar
  module's click actions. Tracked copy of `~/.local/bin/wayle-theme`; copy
  changes back manually (or symlink it) when editing.
