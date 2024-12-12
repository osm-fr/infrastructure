# Journal de bord d'osm33

## 2024-12-12 - cquest

Mise à jour proxmox 8.3.1 faite et reboot.

## 2023-07-14 - cquest

FAIT:
- Reboot hard du serveur, bloqué suite à une saturation de l'espace disque.
- mise en place d'un quota de 300Go pour le mirror des fichier planet + réduction de la rétention à 20 jours (4 planet maximum)
- apt-update / dist-upgrade  après reboot
- zpool trim 

Prêt pour upgrade vers Proxmox 8 (vérifié avec pve7to8)

## 2023-07-15 - cquest

La température du SSD nvme0 monte chaque heure au delà de 60°.
C'est dû à osm2pgsql du CT100 qui fait les mises à jour sur les diff horaire ce qui provoque:
- un pic d'écritures sur le SSD
- un pic de charge CPU

Le SSD étant physiquement derrière les CPU, il se prend un coup d'air chaud et chauffe lui même plus avec les écritures.

FAIT:
- **J'ai réduit le nombre de threads d'osm2pgsql de 8 à 4** dans le CT100 pour voir si cela réduit ce pic en lissant un peu les mises à jour.

Autre info de contexte: le datacenter TH3 n'est plus à 18° mais plutôt à 22/23°... ceci n'est pas négligeable.

## 2023-07-28 - cquest

Remplacement de atime par relatime sur les pool ZFS, afin de limiter les écritures.
Globalement une précision à la journée sur le dernier accès est amplement suffisante.
Cela limitera l'usure des SSD... et la taille des snapshots donc le temps de réplication.

## 2023-08-03 - jocelyn

Suite à panne temporaire d'osm11/osm13, installation d'un rendu cyclosm sur le CT renderd.th3 (+ compte pgsql `cyclosm` sur osm2pgsql.th3), sans countours ni ombrages. http://tile.openstreetmap.fr a été temporairement basculé sur ce rendu le lendemain, avant que osm11 ne soit rétabli.

## 2023-08-09 - jocelyn

/rpool est plein, du coup nettoyage:
  - suppression du rendu cyclosm (et tuiles) de renderd.th3
  - suppression des fichiers de /rpool/tiles/fr/20
  - ajout de /rpool/reservation de 20G pour garder de la place vide pour la prochaine fois
    ```
    zfs create rpool/reservation
    zfs set reservation=20G rpool/reservation
    ```

La page web proxmox affiche toujours osm33 en non-connecté - un reboot risque d'être nécessaire comme début juillet.

## 2023-08-10 - jocelyn

Reboot du host avec `systemctl --force reboot`.

## 2024-01-06 - cquest

Mise à jour en Proxmox 8
zpool trim sur les SSD
Mise à jour de PG 15 > 16 sur le conteneur osm2pgsql
