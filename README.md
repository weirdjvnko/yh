# yh
sudo mkdir -p /mnt/nvme-top/cachy &amp;&amp; for s in /mnt/rescue-top/@*; do n=$(basename "$s"); [ "$n" = "@tmp" ] &amp;&amp; continue; echo "=== $n"; sudo btrfs subvolume create "/mnt/nvme-top/cachy/$n" &amp;&amp; sudo rsync -aHAXS --numeric-ids --info=progress2 --exclude='.snapshots' "$s/" "/mnt/nvme-top/cachy/$n/" || echo "!!! ОШИБКА на $n"; done
