## undeprecated-overlay

This is an overlay for fixing the mistakes Gentoo has made. Some examples of this are:

- Forcing `libglvnd` and removing `eselect-opengl`[1]
- Removing `consolekit`, it's USE flags from any ebuilds using it preventing anyone from keeping it[2]

[1] Sorry, we LITERALLY CAN NOT help with this. Removing the package mask and forced `libglvnd` use flag<br>
will cause `emerge` to silently ignore `x11-base/xorg-server`, `media-libs/mesa`, and `eselect-opengl`.

[2] You must edit `/var/db/repos/gentoo/profiles/base/use.mask` and remove the `consolekit` entry<br>
for the `consolekit` USE flag to work.

## Installation

- Copy `undeprecated.conf` to `/etc/portage/repos.conf` if it's a dir, or append it if it's a file
- Sync repos

## Software

Included:

- `sys-auth/consolekit`
- `sys-auth/polkit`
- `x11-drivers/nvidia-drivers-{340xx,390xx}`
