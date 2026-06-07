kubectl create namespace immich

https://github.com/oskariheino/raspberrypi/tree/main/immich

sudo rsync -a --info=progress2 source/ /destination


Backup useful commands

lsblk : to see drive 
sudo mount -o uid=1000,gid=1000 /dev/sda2 /mnt/hdd
sudo umount /mnt/hdd
sudo udisksctl power-off -b /dev/sda

backup with restic

restic -r /path/to/immich-repo backup /path/to/immich --verbose


backup restore:

1. stop the current pod
2. gzip -dc /data/immich/backups/backup to restore |
sed '/^\\restrict /d; /^\\unrestrict /d' |
kubectl exec -i -n immich immich-database-1 -- \
  psql -U postgres -d app --single-transaction -v ON_ERROR_STOP=1