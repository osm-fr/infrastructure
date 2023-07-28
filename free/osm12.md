# Journal de bord d'osm12

## 2023-07-28 - cquest

Remplacement de atime par relatime sur les pool ZFS, afin de limiter les écritures.
Globalement une précision à la journée sur le dernier accès est amplement suffisante.
Cela limitera l'usure des SSD... et la taille des snapshots donc le temps de réplication.
