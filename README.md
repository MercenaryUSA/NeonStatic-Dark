# Neon Static Dark

A darker take on [Neon Static](https://github.com/MercenaryUSA/NeonStatic), a cyberpunk theme for Discord made for [Vencord](https://vencord.dev). It also works in BetterDiscord and other client mods that load `.theme.css` files.

Neon Static Dark keeps everything that defines Neon Static (chamfered corners, scanlines, a faint grid, glitchy hovers), but pushes the surfaces close to pure black and tones the neon down. It is meant for dark rooms, OLED screens and long late-night sessions where the original feels too bright.

## How it differs from Neon Static

| | Neon Static | Neon Static Dark |
|---|---|---|
| App frame | `#07060d` | `#030307` |
| Chat background | `#0c0b16` | `#06050c` |
| Raised panels | up to `#231f3f` | up to `#18152f` |
| Cyan accent | `#36e2f0` | `#1fc8d6` (deeper) |
| Magenta accent | `#ff3ea5` | `#e0268c` (deeper) |
| Main text | `#c9cce6` | `#b4b7d4` (dimmer) |
| Borders | slightly brighter | fainter hairlines |
| Background grid | `0.035` | `0.025` (fainter) |

## What it looks like

- **Surfaces:** almost-black indigo, with only small steps between layers.
- **Accents:** deep neon cyan as the main accent, magenta as the second, a muted yellow for mentions. The neon traces edges and selected items and never fills large areas.
- **Shape:** small radii and clipped, "chamfered" corners on buttons, embeds and the user panel.
- **Atmosphere:** a faint grid behind the chat, a subtle CRT scanline overlay and a soft neon haze in the corners.
- **Type:** [Chakra Petch](https://fonts.google.com/specimen/Chakra+Petch) for text, [Orbitron](https://fonts.google.com/specimen/Orbitron) for headers and labels, [JetBrains Mono](https://www.jetbrains.com/lp/mono/) for code.
- **Motion:** menus and popouts pop in, messages fade up, neon elements flicker on like a tube catching, and channel names glitch with an RGB split on hover.

All animation is skipped when Reduce Motion is on, either in Discord's settings or in your operating system.

## Install

### Vencord: online theme (auto-updates)

1. Open **Settings → Vencord → Themes → Online Themes**.
2. Paste this link and save:

   ```
   https://raw.githubusercontent.com/MercenaryUSA/NeonStatic-Dark/main/NeonStaticDark.theme.css
   ```

### Vencord: local file

1. Download [`NeonStaticDark.theme.css`](NeonStaticDark.theme.css).
2. Open **Settings → Vencord → Themes → Open Themes Folder** and drop the file in.
3. Enable **Neon Static Dark** in the theme list.

### BetterDiscord

Put `NeonStaticDark.theme.css` in your BetterDiscord `themes` folder and enable it under **Settings → Themes**.

Use Discord's **Dark**, **Darker** or **Midnight** appearance. The light theme is not styled. Only enable one of Neon Static or Neon Static Dark at a time.

## Customize

Everything is driven by the variables in section 1 (**KNOBS**) at the top of the file. Edit them in a local copy, or override them in Vencord's **QuickCSS**:

```css
:root {
    --cp-cyan: #1fc8d6;        /* main accent */
    --cp-magenta: #e0268c;     /* second accent */
    --cp-bg-1: #06050c;        /* chat background */
    --cp-scanlines: 0.035;     /* CRT scanlines, 0 turns them off */
    --cp-grid: 0.025;          /* grid behind the chat, 0 turns it off */
    --cp-glow-strength: 1;     /* 0 = no neon glow */
    --cp-notch: 8px;           /* size of the chamfered corners */
}
```

Discord also builds many colours from its own `--neutral-*` and `--blurple-*` scales, which the theme recolours in section 2. If you change the accent hue, update the hue in the `--blurple-*-hsl` lines to match.

## Notes

Discord's CSS class names include a short hash (for example `.message_SY_P2T`) that can change when Discord ships an update. If part of the theme stops applying after an update, the matching class needs to be looked up again.
