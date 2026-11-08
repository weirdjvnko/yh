# yh

rm -f /var/lib/pacman/db.lck; pacman -Syu


p=$(pacman -Qkq 2>/dev/null | cut -d' ' -f1 | sort -u); [ -n "$p" ] && pacman -S $p


pacman -S linux-cachyos linux-cachyos-headers linux-cachyos-lts linux-cachyos-lts-headers


grub-install --target=x86_64-efi --efi-directory=/boot/efi --bootloader-id=cachyos


grub-mkconfig -o /boot/grub/grub.cfg



ls /boot; grep -m3 "linux.*root=" /boot/grub/grub.cfg
