# yh
sudo btrfs subvolume create /mnt/nvme-top/cachy/@/.snapshots

sudo mkdir -p /mnt/new


sudo mount -o subvol=/cachy/@ /dev/nvme0n1p3 /mnt/new

sudo arch-chroot /mnt/new

mount -a; grep -v '^#' /etc/fstab; ls /boot /boot/efi/EFI; pacman -Qqs '^linux-cachyos'


