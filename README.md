# Rofi emoji plugin

An emoji selector plugin for Rofi that copies the selected emoji to the
clipboard.

## Usage

Run rofi like:

```bash
rofi -show emoji -modi emoji
```

| Key              | Effect                  |
|------------------|-------------------------|
| <kbd>Enter</kbd> | Copy emoji to clipboard |

**Note:** If you change your keybind for `kb-accept`, then your change will
also apply here.

## Screenshot

![Screenshot showing a Rofi window searching for emojis containing "uni", the
emoji for "Unicorn face" being selected](screenshot.png)

## Installation

<a href="https://repology.org/metapackage/rofi-emoji/versions">
    <img src="https://repology.org/badge/vertical-allrepos/rofi-emoji.svg" alt="Packaging status" align="right">
</a>

**Dependencies**

| Dependency | Version      |
|------------|--------------|
| rofi       | 1.4 (or git) |

**Optional dependencies**

In order to actually use rofi-emoji some "adapters" need to be installed, as
appropriate for your environment.

| Dependency   | Notes                        |
|--------------|------------------------------|
| xsel         | For X11.                     |
| xclip        | For X11.                     |
| wl-clipboard | For Wayland. (**Untested!**) |

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

If you plan on developing the code and want to test the plugin, you can also
run `./run-development.sh`, which will do all setup steps for you and then
start Rofi using the locally compiled plugin and clipboard adapter script. This
will not affect your system and does not require root.

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

This plugin is released under the MIT license. See `LICENSE` for more details.

[emoji-data]: https://github.com/Mange/emoji-data
