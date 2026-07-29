# Journal de bord d'osm37 (serveur Panoramax)

## 2026-07-29 - cquest

Mise à jour en Proxmox 9
Ajout de 5 disques 8To pour étendre le pool (RAIDZ expansion)
Mise à jour driver NVidia en v580.173 sur le host et le conteneur 200 du backend de floutage

Récap sur https://forum.openstreetmap.fr/t/instance-panoramax-osm-fr-linfra/13428/63


## 2026-03-10

Remplacement et reformatage d'un disque dur:
- Un disque de 8To (sdaw) avait un nombre croissant de bad blocks et le test SMART long ne passait plus depuis quelques temps.
- ZFS gérait ça comme il faut, mais le remplacement devenait nécessaire.
- Je l'ai donc remplacé par le disque spare disponible.
- Une fois le remplacement fait, j'ai fait un formatage de bas niveau (sg_format), puis refait un test SMART complet et le disque semble à nouveau bon pour le service malgré 3 bas blocks.
- Je l'ai remis en spare dans le pool "pano".


## 2025-05-06

Ajout de 12 disques de 16To dans la baie de stockage
- Test SMART long OK pour tous
- Reformatage en 4096 octets (suppression du "Type 2 protection" qui posait problème avec ZFS)

Les disques sont en test sur un pool séparé "test".
