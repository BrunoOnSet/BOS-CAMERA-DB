BOS_CAMERA_DB V1.6
====================

Mise à jour : 2026-08-20

Nouveauté principale
--------------------
Ajout d'un bloc `waveformGuide` aux profils Blackmagic afin que BOS EXPO puisse
lire directement depuis la base les repères de waveform pour :
- Video
- Extended Video
- Film Gen 5
- Film Gen 4 / Blackmagic 4.6K Film sur URSA Mini Pro 4.6K G2

Méthode
-------
Gen 5 :
- Film : fonction de transfert Blackmagic Film Gen 5.
- Video / Extended Video : axe neutre calculé à partir des LUT Blackmagic
  `Blackmagic Gen 5 Film to Video.cube` et
  `Blackmagic Gen 5 Film to Extended Video.cube`.

URSA Mini Pro 4.6K G2 / Gen 4 :
- Video / Extended Video : axe neutre calculé depuis
  `Blackmagic 4.6K Film to Video v4.cube` et
  `Blackmagic 4.6K Film to Extended Video v4.cube`.
- Les positions en stops sont basées sur une table historique de repères
  Blackmagic 4.6K Film et sont explicitement marquées approximatives.

Valeurs centrales dérivées
--------------------------
Gen 5 :
- Video : gris 18 % -> 40.23 %
- Extended Video : gris 18 % -> 41.10 %

Gen 4 / 4.6K G2 :
- Video v4 : gris 18 % -> 41.12 %
- Extended Video v4 : gris 18 % -> 41.06 %

Important
---------
Les LUT Blackmagic originales ne sont PAS incluses dans ce ZIP.
La DB conserve leur nom et leur SHA-256 pour traçabilité.

Les données DOF, MEDIA et les sensibilités de V1.5 sont conservées.
