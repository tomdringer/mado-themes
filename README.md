# mado-themes

Community themes for [Mado](https://github.com/tomdringer/mado), a terminal multiplexer built with Rust and Slint.

## Installing a theme

1. Download the `.toml` file for the theme you want.
2. Place it in `~/.config/mado/themes/`.
3. Set `theme = "name"` in `~/.config/mado/config.toml` (the filename without `.toml`).
4. Restart Mado.

```toml
# ~/.config/mado/config.toml
theme = "amber"
```

## Theme schema

Themes are TOML files with three sections: `[ui]`, `[starship]` (optional), and `[terminal]` / `[terminal.ansi]` (optional). All colour values are hex strings (`"#rrggbb"`).

### `[ui]`

Controls the Mado interface itself. All fields are required.

| Field | Description |
|-------|-------------|
| `window_bg` | Main window background |
| `terminal_area_bg` | Background behind terminal panes |
| `pane_bg` | Individual pane background |
| `pane_toolbar` | Pane toolbar / tab bar |
| `focus_border` | Border colour of the focused pane |
| `active_dot` | Active session indicator dot |
| `card_bg` | Sidebar card background |
| `card_border` | Sidebar card border |
| `divider_active` | Pane divider handle when dragging |
| `divider_inactive` | Pane divider handle at rest |
| `text_primary` | Primary text colour |
| `text_muted` | Secondary / muted text colour |
| `welcome_border` | Welcome banner box border (optional, defaults to `focus_border`) |
| `welcome_muted` | Welcome banner subtitle text (optional, defaults to `text_muted`) |
| `welcome_dim` | Welcome banner hint text (optional, defaults to `text_muted`) |

### `[starship]`

Optional. When `theme_starship = true` is set in your Mado config, Mado writes a Starship palette using these colours, so your prompt matches the active theme without changing your prompt layout or segments.

The colour role names mirror the [Gruvbox Starship preset](https://starship.rs/presets/gruvbox-rainbow) so any format string built around that palette works unchanged.

| Field | Segment |
|-------|---------|
| `color_fg0` | Text on all segments |
| `color_bg1` | Time segment (darkest background) |
| `color_bg3` | Docker / conda segment |
| `color_blue` | Language / runtime segment |
| `color_aqua` | Git segment |
| `color_yellow` | Directory segment |
| `color_orange` | OS / user segment (rightmost, brightest) |
| `color_green` | Success prompt character |
| `color_purple` | Vim replace mode indicator |

All segment background colours should be dark enough for light text — aim for at least 4.5:1 contrast ratio against `color_fg0`.

### `[terminal]` and `[terminal.ansi]`

Optional. Sets the 16-colour ANSI palette and default foreground/background for terminal panes.

```toml
[terminal]
foreground = "#cccccc"
background = "#1e293b"

[terminal.ansi]
black          = "#1e2030"
red            = "#f7768e"
green          = "#9ece6a"
yellow         = "#e0af68"
blue           = "#7aa2f7"
magenta        = "#bb9af7"
cyan           = "#7dcfff"
white          = "#c0caf5"
bright_black   = "#464858"
bright_red     = "#ff9eb6"
bright_green   = "#c6f692"
bright_yellow  = "#ffd790"
bright_blue    = "#a2caff"
bright_magenta = "#e3c2ff"
bright_cyan    = "#a5f7ff"
bright_white   = "#e8f2ff"
```

## Example

See [`themes/gray.toml`](themes/gray.toml) for a minimal working example, or [`themes/blue.toml`](themes/blue.toml) for one with all optional sections filled in.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).
