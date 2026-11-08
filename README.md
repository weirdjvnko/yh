# yh

sudo mkdir -p /mnt/nvme-top/cachy && for s in /mnt/rescue-top/@*; do n=$(basename "$s"); [ "$n" = "@tmp" ] && continue; echo "=== $n"; sudo btrfs subvolume create "/mnt/nvme-top/cachy/$n" && sudo rsync -aHAXS --numeric-ids --info=progress2 --exclude='.snapshots' "$s/" "/mnt/nvme-top/cachy/$n/" || echo "ERROR on $n"; done
