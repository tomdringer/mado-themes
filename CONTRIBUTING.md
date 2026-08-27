# Contributing a theme

Thanks for wanting to contribute. Themes are reviewed and merged by the Mado maintainer. The bar is low — it just needs to look good and be readable.

## Steps

1. **Fork** this repository and create a branch named after your theme (e.g. `theme/tokyo-night`).

2. **Copy the template** and rename it:
   ```
   cp template.toml themes/your-theme-name.toml
   ```
   The filename becomes the theme name users put in their config, so keep it lowercase, no spaces (hyphens are fine).

3. **Fill in all required `[ui]` fields.** The `[starship]` and `[terminal]` sections are optional but appreciated.

4. **Test it** by placing your file in `~/.config/mado/themes/` and setting `theme = "your-theme-name"` in `~/.config/mado/config.toml`.

5. **Check contrast.** Text must be readable on every background colour. A quick way to test: open Mado with your theme and make sure the welcome banner, sidebar, and pane toolbars all look clean. For Starship segment colours, every background in the `[starship]` section should have at least 4.5:1 contrast against `color_fg0`.

6. **Open a pull request** against `main`. Include a short description of the palette (e.g. "dark blue based on Tokyo Night") and, if you have one, a screenshot.

## Guidelines

- **One theme per PR.** Makes review and rollback straightforward.
- **Name collisions.** If a theme with your name already exists, pick a more specific name (e.g. `tokyo-night-storm` instead of `tokyo-night`).
- **No generated files.** Don't commit lockfiles, `.DS_Store`, editor config, etc.
- **Colours must be 6-digit hex** (`#rrggbb`). Shorthand (`#rgb`) is not supported.
- **Dark themes only for now.** Light theme support is planned but not yet implemented in Mado.

## What gets reviewed

- Does it look intentional? Random colours won't be merged.
- Are required `[ui]` fields all present?
- Is text readable on all backgrounds?
- Is the filename lowercase and hyphen-separated?

That's it. No strict colour count, no required palette source.
