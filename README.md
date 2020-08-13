## undeprecated-overlay

This is an overlay for fixing the mistakes Gentoo has made. Some examples of this are:

- Forcing `libglvnd` and removing `eselect-opengl`\*
- Removing `consolekit`, it's USE flags from any ebuilds using it preventing anyone from keeping it

\* Sorry, we LITERALLY CAN NOT help with this. Removing the package mask and forced `libglvnd` use flag<br>
will cause `emerge` to silently ignore `x11-base/xorg-server`, `media-libs/mesa`, and `eselect-opengl`.

## Installation

- Copy `undeprecated.conf` to `/etc/portage/repos.conf` if it's a dir, or append it if it's a file
- Sync repos

## Software

Included:

- `sys-auth/consolekit`
- `sys-auth/polkit`
- `x11-drivers/nvidia-drivers-{340xx,390xx}`
