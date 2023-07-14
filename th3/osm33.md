# Journal de bord d'osm33

## 2023-07-14 - cquest

Reboot hard du serveur, bloqué suite à une saturation de l'espace disque.
- mise en place d'un quota de 300Go pour le mirror des fichier planet + réduction de la rétention à 20 jours (4 planet maximum)
- apt-update / dist-upgrade  après reboot
- zpool trim 

Prêt pour upgrade vers Proxmox 8 (vérifié avec pve7to8)
