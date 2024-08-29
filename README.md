# htv-dotfiles

HTV04's **awesome** dotfiles!

The official repository can be found [here](https://codeberg.org/HTV04/htv-dotfiles), in case you're looking at a fork/mirror.

> [!NOTE]
> Nothing crazy here right now, as I'm still figuring out what to include, and how to do so. My goal with this repository is to provide an optimal configuration without anything unnecessary or user-specific. In other words, expect more stuff very soon.

## Dependencies

* [Chezmoi](https://www.chezmoi.io/) (Dotfile manager)
* [Vi](https://ex-vi.sourceforge.net/) (Default editor, intended for small files)

## Configured software

* [Bash](https://www.gnu.org/software/bash/) (Backup shell)
* [Bat](https://github.com/sharkdp/bat)
* [Electron](https://www.electronjs.org/) (Configured for Wayland)
* [Foot](https://codeberg.org/dnkl/foot) (Preferred terminal)
* [Git](https://git-scm.com/)
* [Makepkg](https://pacman.archlinux.page/)
* [Paru](https://github.com/Morganamilo/paru)
* [POSIX shell](https://pubs.opengroup.org/onlinepubs/9799919799/utilities/V3_chap02.html) ([DASH](http://gondor.apana.org.au/~herbert/dash/) is the preferred login shell, sources [`.profile`](.profile))
* [SDL](https://www.libsdl.org/) (Configured for Wayland)
* [Zsh](https://www.zsh.org/) (Preferred shell)

Additional files:

* [Firefox](https://mozilla.org/firefox) preferences, generated with [Firefox Profile Maker](https://ffprofile.com/)
* [Konsole](https://konsole.kde.org/) profile and color schemes
* [OpenDoas](https://github.com/Duncaen/OpenDoas) configuration
* [Pacman](https://pacman.archlinux.page/) configuration
* [Plasma](https://kde.org/plasma-desktop/) color schemes

## `htv-local`

The layout of the [`htv-local`](htv-local) directory is based on that of the [Unix filesystem](https://en.wikipedia.org/wiki/Unix_filesystem#Conventional_directory_layout). Any custom binaries, scripts, and other support files that do not have an official directory are available here.

## Installation

To begin installation, run `chezmoi init [repository url]`. You will be prompted for the following:

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
