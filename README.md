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
