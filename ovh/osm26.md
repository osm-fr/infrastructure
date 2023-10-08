# Journal de bord d'osm26

# 2023-08-13 - OVH

Blocage des emails par OVH, suite à détection de spam, surement sur liste.openstreetmap.fr

# 2023-10-08 - jocelyn

Application de la modif de @anayrat pour la config du kernel (swappiness/huge-pages) - https://github.com/osm-fr/ansible-scripts/pull/96

Reboot du host pour appliquer l'ajout des huge-pages.
Deux soucis après reboot:
  - mobilizon déclenche une erreur, surement à cause d'une mise à jour effectuée à moitié précédemment. Réparation effectué après discussion sur https://github.com/osm-fr/ansible-scripts/pull/96.
  - taginfo n'affiche pas correctement la liste des clés populaires.

On a 3MB de hugepages utilisés, mais ce host n'a pas de grosses bases postgresql, du coup, c'est attendu.
