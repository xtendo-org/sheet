## TuxOnIce

([TuxOnIce] on Arch Wiki)

1. Install linux-ice and tuxonice-userui from AUR.
1. Edit `/etc/hibernate/tuxonice.conf`:
    - `ProcSetting userui_program /usr/bin/tuxoniceui`
1. Edit `/etc/mkinitcpio.conf`:
    - `userui` before `resume` hook
1. `sudo mkinitcpio -p linux-ice`
1. `sudo grub-mkconfig -o /boot/grub/grub.cfg`

[TuxOnIce]: https://wiki.archlinux.org/index.php/TuxOnIce
