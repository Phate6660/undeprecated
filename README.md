## undeprecated-overlay

This is an overlay for fixing the mistakes Gentoo has made. Some examples of this are:

- Forcing `libglvnd` and removing `eselect-opengl`
- Removing `consolekit`, it's USE flags from any ebuilds using it preventing anyone from keeping it

## Installation

- Copy `undeprecated.conf` to `/etc/portage/repos.conf` if it's a dir, or append it if it's a file
- Sync repos

## Software

Included:

- `sys-auth/consolekit`

Planned to be included:

- `app-eselect/eselect-opengl`
- `app-eselect/eselect-opencl`
- `x11-drivers/nvidia-drivers-{390xx,430xx}`
- `media-libs/mesa` (without forced libglvnd)
- `x11-base/xorg-server` (without forced libglvnd)
