# Spectra — Quattro

A dark charcoal and periwinkle theme with restrained frosted-glass surfaces,
native to **Omarchy 4.0.4+**. Based on
[abhijeet-swami's Spectra](https://github.com/abhijeet-swami/omarchy-spectra-theme).

## Install

After the migrated version is published:

```bash
omarchy theme install https://github.com/henningmyhrvold/omarchy-spectra-theme
```

For this three-repo workstation collection, use the local checkout instead:

```bash
bash ~/src/omarchy-dotfiles/scripts/omarchy-mods-desktop.sh
```

That installer links this checkout as `spectra`, adds the compositor's rounded
corners and blur through user configuration, and applies the theme. It preserves
existing files in timestamped backups. Reapply theme edits with:

```bash
omarchy theme set spectra
```

## Theme structure

- `colors.toml`: Quattro's named palette, original ANSI colors, selection/cursor
  colors, and declarative window-border gradients.
- `shell.toml`: native bar, menu, notification, popup, tooltip, OSD (popup
  tokens), polkit, image-picker, and lock-screen surfaces. The `[launcher]`
  section is not read by this Omarchy version and is harmless there.
- `backgrounds/`: the original Spectra wallpapers.
- App-specific color-only files remain for apps such as btop and Helix.

Omarchy generates terminal, Hyprland, Gum, Neovim and VS Code files from its
current templates. This also works with `omarchy theme install`, which filters
Lua and terminal configs out of cloned themes. Old Waybar/Walker/Mako/SwayOSD
and Hyprlock files were retired; their originals remain in Git history.

## Glass settings

Background alpha is 0.4 for the bar, menu, popups, tooltip, polkit, and the
(unused) launcher section, 0.90 for notifications, and 0.85 for the lock
screen. Text stays fully opaque. Adjust these in `shell.toml` and reapply.
Keep `bar.transparent` **false** in `~/.config/omarchy/shell.json`: true makes
the bar background completely invisible instead of using the theme's alpha.

Blur, shadows, gaps, and square corners (`rounding = 0`) are workstation
preferences in the companion dotfiles' `hypr/looknfeel.lua` (`gaps_in`/`gaps_out`
4, `border_size` 2, blur size 6/passes 3, shadow range 18). Quattro's shell
follows Hyprland's rounding automatically. A theme installed alone still has
the palette and translucent surfaces, but uses the user's existing compositor
geometry/blur.

The images in `screenshots/` and `preview.png` are historical Omarchy 3
references, not screenshots of the migrated Quattro shell.
