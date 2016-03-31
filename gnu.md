## TuxOnIce

([TuxOnIce] on Arch Wiki)

#. Install linux-ice and tuxonice-userui from AUR.
#. Edit `/etc/hibernate/tuxonice.conf`:
    - `ProcSetting userui_program /usr/bin/tuxoniceui`
#. Edit `/etc/mkinitcpio.conf`:
    - `userui` before `resume` hook
#. `sudo mkinitcpio -p linux-ice`
#. `sudo grub-mkconfig -o /boot/grub/grub.cfg`

[TuxOnIce]: https://wiki.archlinux.org/index.php/TuxOnIce
