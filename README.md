# Ulauncher Rofi Everforest

A rofi inspired Everforest theme for Ulauncher 5: compact rows, a monospace font and a green selection bar.

Built for GNOME on Wayland, where rofi itself cannot run, so you can still get the rofi look.

![Demo](assets/demo.gif)

## Features

- Compact rofi style rows (about 42px instead of 70px)
- Slim input bar with green query text
- Small icons aligned to the left edge like rofi
- Monospace font for the query and results
- Everforest colors with a green highlight on the selected row
- No rounded corners, borders or shadows
- Clean look both with and without results

## Requirements

- Ulauncher 5.x (tested on 5.15.15)
- GTK 3.20 or newer
- A monospace font. Fira Mono is used if installed, otherwise it falls back to JetBrains Mono, Noto Sans Mono or your system monospace font.

To get the exact look, install Fira Mono:

```bash
# Fedora
sudo dnf install mozilla-fira-mono-fonts
```

On other distros, install Fira Mono from your package manager or from [Google Fonts](https://fonts.google.com/specimen/Fira+Mono).

## Installation

1. Clone the repo into the Ulauncher themes folder:

   ```bash
   mkdir -p ~/.config/ulauncher/user-themes
   git clone https://github.com/chamals3n4/ulauncher-rofi-everforest.git \
     ~/.config/ulauncher/user-themes/rofi-dark
   ```

2. Restart Ulauncher:

   ```bash
   pkill ulauncher; ulauncher --hide-window &
   ```

3. Open Ulauncher Preferences and choose **Rofi Dark** under **Color Theme**.

## Customization

All colors live at the top of `theme.css`:

```css
@define-color bg      #2f383e;  /* result list */
@define-color bg_alt  #374247;  /* input bar */
@define-color fg      #d3c6aa;  /* text */
@define-color green   #a7c080;  /* selection and query */
```

The color used for matched letters in the results is set in `manifest.json` under `matched_text_hl_colors`.

Other things you can tweak in `theme.css`:

| What | Where |
| --- | --- |
| Font and font size | `.input` and `.item-name` |
| Row height | `.item-container` (negative top and bottom margin) |
| Icon size | `.item-icon` (`-gtk-icon-transform: scale(...)`) |
| Input bar height | `.app > box:first-child` |

## Showing apps on an empty query

Rofi lists all apps as soon as it opens. Ulauncher 5 cannot do that: it shows at most 9 results and has no scrolling list.

The closest option is to show your most used apps when the query is empty. Open Preferences and set **Number of frequent apps to show** to 9.

## Limitations

These come from Ulauncher 5 itself and cannot be fixed with CSS:

- No rofi mode switcher bar (All, apps, windows, run, ssh)
- At most 9 results at a time
- Window width is fixed by Ulauncher

## Credits

- Colors from the [Everforest](https://github.com/sainnhe/everforest) palette by sainnhe
- Look inspired by [rofi-everforest](https://github.com/dennis-n-schneider/rofi-everforest)
- [Ulauncher](https://ulauncher.io)

## License

Released under the MIT License. See [LICENSE](LICENSE) for details.
