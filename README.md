## undeprecated-overlay

This is an overlay for fixing the mistakes Gentoo has made. Some examples of this are:

- Forcing `libglvnd` and removing `eselect-opengl`\*
- Removing `consolekit`, it's USE flags from any ebuilds using it preventing anyone from keeping it

\* Sorry, we can not deal with this actually. `use.force` from the gentoo repo overrides the `use.force`<br>
that was previously in this repo. If you don't want to use `libglvnd`, instead you must edit your<br>
`/var/db/repos/gentoo/profiles/base/use.force` and set `libglvnd` to `-libglvnd`.

## Installation

- Copy `undeprecated.conf` to `/etc/portage/repos.conf` if it's a dir, or append it if it's a file
- Sync repos

## Software

Included:

- `app-eselect/eselect-opencl`
- `app-eselect/eselect-opengl`
- `sys-auth/consolekit`
- `x11-drivers/nvidia-drivers-{340xx,390xx}`
