# Journal de bord d'osm34

## 2025-12-19 - cquest

Migration de rpool sur le nouveau SSD

Comme le nouveau SSD est plus petit que le précédent voici la manip:
- ajout du nouveau SSD au pool avec `zpool add`
- suppression de l'ancien avec `zpool remove`
- ZFS recopie les données du vdev qu'on retire sur l'autre vdev :)

## 2025-12-18 - cquest

Ajout d'un SSD SATA 2.5" en face avant
Migration de rpool sur ce nouveau SSD.

## 2025-06-21 - cquest

Erreurs en lecture sur le SSD SATA (sda).
Un scrub ZFS indique 26 erreurs de lecture, certains fichiers umap sont impactés et quelques logs:
- migration des données uMap sur le SSD NVMe, avec récupération des répliques depuis osm32
- toutes les erreurs sont corrigées
- réplique remise en place vers osm35, puis osm32 (le 24-06-2025)

## 2024-12-12 - cquest

Mise à jour proxmox 8.3.1 faite et reboot.

## 2023-08-09 - jocelyn

Suite à saturation du disque osm33, suppression de ~60 snapshots umap utilisé pour les backups journaliers sur osm32.
Umap a pris +40G en 3 mois - à vérifier si c'est normal.

## 2024-01-06 - cquest

Mise à jour Proxmox 8

Migration des conteneurs sur osm35, non remis pour le moment sur osm34
