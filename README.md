## undeprecated-overlay

This is an overlay for fixing the mistakes Gentoo has made. Some examples of this are:

- Forcing `libglvnd` and removing `eselect-opengl`
- Removing `consolekit`, it's USE flags from any ebuilds using it preventing anyone from keeping it

Table of Contents:

- [Installation](#installation)
- [Software](#software)
- [How To...](#how-to)
- [Contribution](#contribution)

## Installation

- Copy `undeprecated.conf` to `/etc/portage/repos.conf` if it's a dir, or append it if it's a file
- `emerge --sync undeprecated-overlay`

## Software

Included:

- `app-eselect-eselect-opencl`
- `app-eselect-eselect-opengl`
- `media-libs/mesa` (without forced `libglvnd` USE flag)
- `sys-auth/consolekit`
- `sys-auth/polkit`
- `x11-base/xorg-server` (without forced `libglvnd` USE flag)
- `x11-drivers/nvidia-drivers-{340xx,390xx}`

## How-To

### Avoid libglvnd

- You must edit `/var/db/repos/gentoo/profiles/base/use.force` and set `libglvnd` to `-libglvnd`
- You must edit `/var/db/repos/gentoo/profiles/package.mask` and remove the `eselect-opengl` entry
- `emerge -avC xorg-server mesa` (include `libglvnd` if you have it)
- `emerge -atv xorg-server::undeprecated-overlay mesa::undeprecated-overlay`
- `emerge -atv1 xf86-input-libinput` (needed to fix input, oneshot to keep it out of `@world`)
- Restart X

### Use consolekit

- `emerge -atv consolekit::undeprecated-overlay`

If you use polkit:

- `emerge -avC polkit`
- You must edit `/var/db/repos/gentoo/profiles/base/use.mask` and remove the `consolekit` entry for the `consolekit` USE flag to work
- Set the `consolekit` USE flag
- `emerge -atv polkit::undeprecated-overlay`, `consolekit` from the overlay will automatically be pulled in as a dep

## Contribution

We'd love if you'd contribute to the overlay! Is your favorite software being removed from Gentoo?
Get its files, make a pull request to put it here!

Don't want to make a pull request? Make an issue about support for that software! We'll add it!
