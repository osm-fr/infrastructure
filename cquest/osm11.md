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
