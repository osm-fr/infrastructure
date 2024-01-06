# Journal de bord d'osm32

## 2023-07-14 - cquest

**rpool quasi saturé** (97%), besoin de faire de la place avant que ZFS ne bloque tout, il est déjà très lent et il faudrait rester en dessous de 90%

- suppression de snapshots du backup des data umap qui occupent 272Go, **rpool maintenant à 94%**
 ```
  for S in $(zfs list -t snap rpool/backups/umap-data -H -o name | head -n -14); do echo $S; zfs destroy $S;done
  ```
- apt update / dist-upgrade (43 packages mis à jour)
- zpool trim

## 2024-01-06 - cquest

Mise à jour Proxmox 8
