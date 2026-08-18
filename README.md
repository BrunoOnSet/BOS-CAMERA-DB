# BOS Camera Database — v1.1

Base caméra commune à l'écosystème BOS.

## V1.1
- Ajout des 4 caméras Blackmagic déjà présentes dans MEDIA.
- Ajout d'un bloc `media` dans les caméras disposant de presets d'enregistrement.
- FRAME continue de lire `sensorWidthMm`.
- DOF continue de lire `dof`.
- MEDIA lit maintenant `media.modes`.

## Mise à jour
Remplacer uniquement `cameras.json` dans le dépôt GitHub `BrunoSetTools/BOS-CAMERA-DB`.
Les applications gardent un fallback local et la dernière base récupérée pour fonctionner hors ligne.
