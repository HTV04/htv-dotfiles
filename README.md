# htv-dotfiles

HTV04's ***awesome*** dotfiles.

The official repository can be found [here](https://codeberg.org/HTV04/htv-dotfiles), in case you're looking at a fork or mirror.

> [!NOTE]
> Nothing crazy here right now, as I'm still figuring out what to include. My goal with this repository is to provide an optimal configuration without anything unnecessary or user-specific. In other words, expect more stuff very soon.

## Dependencies

* [Chezmoi](https://www.chezmoi.io/): Dotfile manager
* [FiraMono Nerd Font](https://github.com/ryanoasis/nerd-fonts/tree/master/patched-fonts/FiraMono): Font used in terminal emulators
* [OpenDoas](https://github.com/Duncaen/OpenDoas): Privilege elevation
* [Vi](https://ex-vi.sourceforge.net/): Default editor, intended for small files
* [Zsh](https://www.zsh.org/): Shell used for terminal emulators

The login shell must also source [`.profile`](dot_profile). [DASH](http://gondor.apana.org.au/~herbert/dash/) is the preferred login shell.

## Configured software

* [Bash](https://www.gnu.org/software/bash/)
* [Bat](https://github.com/sharkdp/bat): ANSI theme
* [Electron](https://www.electronjs.org/): Wayland support
* [Foot](https://codeberg.org/dnkl/foot)
  * Intended to be used in server and client mode.
* [Git](https://git-scm.com/)
  * Create `~/htv-local/etc/gitconfig` for local configuration.
* [Makepkg](https://pacman.archlinux.page/): Disable package compression
* [Paru](https://github.com/Morganamilo/paru)
* [SDL](https://www.libsdl.org/): Wayland support
* [Zsh](https://www.zsh.org/)

The software in this list is optional, but it's recommended to install them (as applicable) for the best experience.

## Additional files

* [Firefox](https://mozilla.org/firefox) preferences, generated with [Firefox Profile Maker](https://ffprofile.com/): [`~/htv-local/share/firefox-prefs.js`](htv-local/share/firefox-prefs.js)
* [OpenDoas](https://github.com/Duncaen/OpenDoas) configuration: [`~/htv-local/share/doas.conf`](htv-local/share/doas.conf)
* [Pacman](https://pacman.archlinux.page/) configuration: [`~/htv-local/share/pacman.conf`](htv-local/share/pacman.conf.tmpl)
* [Plasma](https://kde.org/plasma-desktop/) color schemes: [`~/.local/share/color-schemes`](dot_local/share/color-schemes)
* [Thunar](https://docs.xfce.org/xfce/thunar/start) custom actions: [`~/.config/Thunar/uca.xml`](private_dot_config/private_Thunar/private_uca.xml)

Most of these files that do not provide any core configuration on their own, but rather are support files that can be used for additional configuration. For example, to install the Firefox preferences file:

> [!WARNING]
> This will delete your existing Firefox profile data.

```sh
rm -r ~/.cache/mozilla/firefox/*.default-release
rm -r ~/.mozilla/firefox/*.default-release/*
cp ~/htv-local/share/firefox-prefs.js ~/.mozilla/firefox/*.default-release/prefs.js
```

## Recommended software

* [Feh](https://feh.finalrewind.org/): Image viewer
* [Firefox](https://mozilla.org/firefox): Web browser
* [Plasma](https://kde.org/plasma-desktop/): Desktop environment
* [Thunar](https://docs.xfce.org/xfce/thunar/start): File manager
  * [thunar-archive-plugin](https://docs.xfce.org/xfce/thunar/archive)
  * [Xarchiver](https://github.com/ib/xarchiver)
* [VLC](https://www.videolan.org/vlc/): Music and video player

This software isn't configured by the dotfiles (with the exception of [additional files](#additional-files)), but I still recommend installing them, as I use them in my personal configurations.

## Environment

### Directory: [`~/htv-local`](htv-local)

The layout of this directory is based on that of the [Unix filesystem](https://en.wikipedia.org/wiki/Unix_filesystem#Conventional_directory_layout). Any custom binaries, scripts, and other support files that do not have an official directory are available here.

In my personal configurations, I use this directory for all of my local files, and it generally assures me that no random applications will write their own files into it.

### Variable: `HTV_TERM`

This variable controls the terminal features used by supported configurations. If set to `full`, text formatting, true color, and [Nerd Fonts](https://www.nerdfonts.com/) symbols will be used. If unset or set to any other value, no terminal features or special characters will be used.

## Installation

To begin installation, run:

```sh
chezmoi init https://codeberg.org/HTV04/htv-dotfiles.git
```

> [!NOTE]
> Mirrors may not be updated as frequently, so you should only replace the URL above if you're using a fork.

You will be prompted for the following:

### Platform

The following platforms are supported:

* Arch Linux: `archlinux`
* Artix Linux: `artixlinux`
* Linux (generic): `linux`
* Unix-like: `unix`

The default will be one of these platforms, if detected. The chosen platform determines which dotfiles will be used and adjusts their contents as necessary.

> [!WARNING]
> The platform detection is not the most optimal. For example, using an Arch-based distribution that isn't listed above will use `linux` as the default. Using the closest option to your platform is preferred, so don't always rely on the default.

### Catppuccin palette

The following [Catppuccin](https://catppuccin.com/) palettes are available:

* Latte: `latte`
* Frappé: `frappe`
* Macchiato: `macchiato`
* Mocha: `mocha`

The default is `latte`. The selected palette will be used as a color scheme where applicable.

## Contributing

Suggestions and fixes are very welcome. However, I won't accept new configurations, or drastic modifications to existing configurations. If you would like to do this, consider creating a fork instead.

## License

"htv-dotfiles" is licensed under the [MIT License](LICENSE).
