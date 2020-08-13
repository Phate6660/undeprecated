## undeprecated-overlay

This is an overlay for fixing the mistakes Gentoo has made. Some examples of this are:

- Forcing `libglvnd` and removing `eselect-opengl`<sup>[1]</sup>
- Removing `consolekit`, it's USE flags from any ebuilds using it preventing anyone from keeping it<sup>[2]</sup>

[1] You must edit `/var/db/repos/gentoo/profiles/base/use.force` and set `libglvnd` to `-libglvnd`.<br>
You must edit `/var/db/repos/gentoo/profiles/package.mask` and remove the `eselect-opengl` entry.

[2] You must edit `/var/db/repos/gentoo/profiles/base/use.mask` and remove the `consolekit` entry<br>
for the `consolekit` USE flag to work.

## Installation

- Copy `undeprecated.conf` to `/etc/portage/repos.conf` if it's a dir, or append it if it's a file
- Sync repos

## Software

Included:

- `app-eselect-eselect-opencl`
- `app-eselect-eselect-opengl`
- `media-libs/mesa` (without forced `libglvnd` USE flag)
- `sys-auth/consolekit`
- `sys-auth/polkit`
- `x11-base/xorg-server` (without forced `libglvnd` USE flag)
- `x11-drivers/nvidia-drivers-{340xx,390xx}`

## Contribution

We'd love if you'd contribute to the overlay! Is your favorite software being removed from Gentoo?
Get its files, make a pull request to put it here!

Don't want to make a pull request? Make an issue about support for that software! We'll add it!
