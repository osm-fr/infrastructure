# Journal de bord d'osm32

## 2025-06-24 - cquest

Création d'un "faux" pool nvme-zfs à l'aide d'un fichier de 2To alloué sur /backups
Ceci va permettre aux repliques de se faire, en particulier celles sur osm34 où les données umap se trouvent désormais sur nvme-zfs.

## 2024-12-12 - cquest

osm12 était freezé depuis plusieurs jours.

Il a rebooté sans problème.

Mise à jour proxmox 8.3.1 faite.

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
