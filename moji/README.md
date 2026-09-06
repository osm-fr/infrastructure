# Cluster MOJI

## Organisation du cluster - répartition des ressources

### osm38 / osm40

Serveurs **sans SSD**, destiné aux CT qui n'ont pas besoin de SSD car générant peu d'I/O (sans base de données importantes):
- site web
- CRM
- nextcloud
- educosm
- petite reine
- garmin
- notes-heatmap
- pleinair

### osm41/osm42

Serveurs **avec SSD NVMe**, destiné aux CT contenant des bases de données nécessitant des I/O rapides où à fort trafic:
- osmose
- comaps

## Serveurs dédiés

### osm39

Serveur **contenant 2 GPU**, utilisé par le backend d'API de floutage de Panoramax

### osm43

Serveur dédié au rendu humanitaire

Il possède 6 HDD de 1To et peut donc avoir une réplique de tout ce qui est stocké sur HDD sur les autres serveurs.

### osm44

Serveur dédié à overpass
