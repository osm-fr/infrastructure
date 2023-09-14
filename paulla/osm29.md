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
