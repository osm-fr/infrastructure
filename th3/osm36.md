# Journal de bord d'osm36

## 2024-01-22 - jocelyn

Reboot du host à nouveau après nouvel import complet du planet. Le log de l'import en était à:
```
2024-01-21 22:41:44  Done postprocessing on table 'planet_osm_nodes' in 0s
2024-01-21 22:41:44  Building index on table 'planet_osm_ways'
2024-01-21 22:41:44  Building index on table 'planet_osm_rels'
```
Et le reboot s'est déclenché à 22:45, du coup, surement pendant la création d'un index.


## 2024-01-21 - jocelyn

Après création d'un CT pour une base osm2pgsql sur le nvme-zfs, l'import initial du planet a été lancé, causant un reboot hard du host complet. Le log IPMI affiche ceci
```
Sat 20 Jan 2024 11:20:54 PM	Critical	120055	Fujitsu	Legacy PCI SERR Bus: 128 Device: 0x02 Function: 0x00	Critical Hardware Errors
Sat 20 Jan 2024 11:20:54 PM	Critical	120067	Fujitsu	PCI: Surprise Down Error Status Bus: 128 Device: 0x02 Function: 0x00	Critical Hardware Errors
Sat 20 Jan 2024 11:20:56 PM	Critical	120047	NMI	Fatal NMI	Critical Hardware Errors
```
où la carte PCI pourrait être le disque NVME ou la carte réseau.

## 2024-01-04 - cquest

Installation initiale du serveur à TH3.
