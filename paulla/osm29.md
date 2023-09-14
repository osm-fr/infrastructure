# Journal de bord d'osm29

## 2023-09-14 - Adrien (teslix)

Test du recordsize à 16K sur le volume de osm211 vers 11H20:
```
zfs set recordsize=16K rpool/data/subvol-211-disk-0
root@osm29:~# zfs get recordsize 
NAME                          PROPERTY    VALUE    SOURCE
rpool                         recordsize  128K     default
rpool/ROOT                    recordsize  128K     default
rpool/ROOT/pve-1              recordsize  128K     default
rpool/data                    recordsize  128K     default
rpool/data/subvol-211-disk-0  recordsize  16K      local
```

Ajout des sondes munin zfs depuis les contrib munin https://github.com/munin-monitoring/contrib/tree/master/plugins/zfs :

```
zfs_arcstats -> /etc/munin/contrib/plugins/zfs/zfs_arcstats
zfsonlinux_stats_cachehitdtype -> /etc/munin/contrib/plugins/zfs/zfsonlinux_stats_
zfsonlinux_stats_cachehitlist -> /etc/munin/contrib/plugins/zfs/zfsonlinux_stats_
zfsonlinux_stats_efficiency -> /etc/munin/contrib/plugins/zfs/zfsonlinux_stats_
zfsonlinux_stats_l2efficiency -> /etc/munin/contrib/plugins/zfs/zfsonlinux_stats_
zfsonlinux_stats_l2utilization -> /etc/munin/contrib/plugins/zfs/zfsonlinux_stats_
zfsonlinux_stats_utilization -> /etc/munin/contrib/plugins/zfs/zfsonlinux_stats_
zpool_capacity -> /home/munin/zpool_capacity
zpool_fragmentation -> /etc/munin/contrib/plugins/zfs/zpool_fragmentation
zpool_iostat -> /etc/munin/contrib/plugins/zfs/zpool_iostat
```

Rollback à 14H41, ça ne marche pas du tout sur hdd ^^:

load average: 72476.38, 23361.04, 9925.69
