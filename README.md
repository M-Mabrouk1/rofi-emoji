# Rofi emoji plugin

An emoji selector plugin for Rofi that can either insert the emoji directly or copy it to the clipboard.

## Usage

Run rofi like:

```bash
rofi -show emoji -modi emoji
```

| Key                               | Effect                  |
|-----------------------------------|-------------------------|
| <kbd>Enter</kbd>                  | Insert emoji            |
| <kbd>Shift</kbd>+<kbd>Enter</kbd> | Copy emoji to clipboard |

**Note:** If you change your keybinds for `kb-accept` or `kb-accept-alt`, then
your changes will also apply here.

## Screenshot

![Screenshot showing a Rofi window searching for emojis containing "uni", the
emoji for "Unicorn face" being selected](screenshot.png)

## Installation

**Dependencies**

| Dependency | Version      |
|------------|--------------|
| rofi       | 1.4 (or git) |

**Optional dependencies**

In order to actually use rofi-emoji some "adapters" need to be installed. A
"copy adapter" is needed for the "Copy" action
(<kbd>Shift</kbd>+<kbd>Enter</kbd>) and an "insert adapter" is needed for the
"Insert" action (<kbd>Enter</kbd>).

| Dependency   | Type           | Notes                                  |
|--------------|----------------|----------------------------------------|
| xsel         | Copy adapter   | For X11.                               |
| xclip        | Copy adapter   | For X11.                               |
| xdotool      | Insert adapter | For X11. Also a Copy adapter for X11.  |
| wl-clipboard | Copy adapter   | For Wayland. (**Untested!**)           |

### Arch Linux

`rofi-emoji` can be installed via [AUR](https://aur.archlinux.org/):
[rofi-emoji](https://aur.archlinux.org/packages/rofi-emoji/)

### Compile from source

`rofi-emoji` uses autotools as build system. Download the source and run the following to install it:

```bash
$ autoreconf -i
$ mkdir build
$ cd build/
$ ../configure
$ make
$ sudo make install
```

## Emoji database

When installing the emoji database (`all_emojis.txt` file) is installed in
`$PREFIX/share/rofi-emoji`. The plugin will search `$XDG_DATA_DIRS` for a
directory where `rofi-emoji/all_emojis.txt` exists in. If the plugin cannot
find the data, make sure `$XDG_DATA_DIRS` is set correctly.

If it is unset it should default to `/usr/local/share:/usr/share`, which works
with the most common prefixes.

### Updating to a newer version

The list is copied from the [Mange/emoji-data][emoji-data] repo.

## License

This plugin is released under the MIT license.

[emoji-data]: https://github.com/Mange/emoji-data
