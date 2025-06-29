# Journal de bord d'osm42

## 2025-06-25 - jocelyn

Remplissage du zfs root, impactant peertube, et le host lui-même, plus accessible sur proxmox.
Libération de place en:
  - utilisant temporairement le subvol reservation
  - déplaçant des réplications d’autres lxc vers d’autres hosts que osm42 (100G de libéré)
Après redémarrage du host, proxmox est reparti correctement.

Pour éviter tout souci sur le root plein dans le futur, j’ai mis une réservation de 15G sur tous les hosts de moji.
