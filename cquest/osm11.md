# Journal de bord d'osm11

## 2023-07-14 - cquest

Le SSD SATA de 2To n'a plus que 9% d'espérance de vie, au rythme actuel de son usage cela donne 9 mois.

SSD de remplacement (4To) commandé.

## 2023-07-16 - cquest

Le SSD de remplacement est arrivé (oui, un dimanche).
Remplacement à faire en fonction des slots dispo et port SATA dispo...

ssd-zfs plein à 97%... j'ai donc fait du ménage:
- déplacement des CT inutilisés sur hdd-zfs
- augmentation de la marge d'espace libre dans le script de nettoyage du cache de cyclosm... 10 -> 100G

Avec ce réglage est maintenant à 89%, ce qui est bien plus safe !

## 2023-07-21 - cquest

**Installation du nouveau SSD SATA** de 4To sur une carte PCIe, connecté sur la port SATA de la carte mère destiné à la base au DVD

Copie lancée par zfs send/recv du cache de tuiles de cyclosm

Copie terminée, bascule de ssd-zfs sur le nouveau SSD, l'ancien pool est temporairement sur ssd-zfs-old

## 2023-07-28 - cquest

Remplacement de atime par relatime sur les pool ZFS, afin de limiter les écritures.
Globalement une précision à la journée sur le dernier accès est amplement suffisante.
Cela limitera l'usure des SSD... et la taille des snapshots donc le temps de réplication.

## 2023-08-05 - cquest

Ajout d'une IPv6 pour osm11 pour permettre à osm23-24 (les caches de tuiles) d'y accéder par deux canaux différents:
- IPv4 : fibre OVH
- IPv6: fibre free

Cela permet ajouter une seconde entrée en upstream "backup" avec l'IPv6 fixe sur la config nginx d'osm23-24 qui basculera d'une fibre à l'autre en cas d'indisponibilité.

Pour plus de résilience, chaque box fibre est maintenant sur une arrivée électrique différente.
