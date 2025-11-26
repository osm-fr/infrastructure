# Journal de bord d'osm12

## 2024-12-11 - cquest

Déplacement à DC1:
- premier reboot: plantage avec un kernel panic dû à une erreur CPU
- second reboot... ça passe et ça freeze peu de temps après

Problème hardware, pas étonnant, ce serveur tourne H24 depuis 12 ans !

Je l'ai ramené chez moi pour voir ce qu'on peut encore en tirer. Il y a au moins les 2 SSD NVMe de 4To à réutiliser (désormais sur osm51/52)

Mise à jour du wiki faite.

## 2024-11-20 - cquest

Panne d'osm12 qui ne répond plus.
- bano.openstreetmap.fr migré sur osm14
- tuiles humanitaires redirigées temporairement vers le rendu osm.org
- contact avec free pour le relancer...

## 2023-07-28 - cquest

Remplacement de atime par relatime sur les pool ZFS, afin de limiter les écritures.
Globalement une précision à la journée sur le dernier accès est amplement suffisante.
Cela limitera l'usure des SSD... et la taille des snapshots donc le temps de réplication.
