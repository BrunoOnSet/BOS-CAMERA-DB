# BOS Camera Database — v1.2

Base caméra commune à l'écosystème BOS.

## V1.2 — Exposition
- Ajout d'un bloc `exposure` aux 11 caméras réelles de la base.
- Sony : FX30 800/2500 ; FX3 800/12800 ; FX5 800/4000/12800 + ISO 800 Dual Gain ; FX6 800/12800 en S-Log3/Cine EI.
- Blackmagic : Pocket 4K/6K 400/3200 ; URSA Mini Pro 4.6K G2 800 ; URSA Mini Pro 12K 800.
- ARRI : ALEXA Mini LF EI 800 (EI 160–3200) ; ALEXA 35 EI 800 (EI 160–6400, Enhanced Sensitivity signalé séparément).
- RED V-RAPTOR VV : ISO 800 est enregistré comme valeur de référence/par défaut, **pas** comme Dual Native ISO.
- Les profils sans Base ISO officiellement publiée (notamment S-Cinetone) restent marqués `notPublished` afin de ne pas inventer de valeur.
- Les capteurs génériques (Full Frame, S35, APS-C, MFT, 1 pouce) n'ont pas de bloc `exposure`.

### Convention du bloc `exposure`
- `unit`: `ISO` ou `EI`.
- `defaultProfile`: profil proposé par défaut par EXPO.
- `profiles.*.baseValues`: vrais ISO/EI de base à surligner uniquement si `baseType` le justifie.
- `referenceValues`: valeur de travail recommandée mais non native (ex. RED).
- `baseType`: `dualBaseISO`, `multiBaseISO`, `dualNativeISO`, `nativeISO`, `baseSensitivity`, `referenceOnly` ou `notPublished`.
- `gain.type`: évite toute conversion ISO/dB générique non documentée.
- `specialModes`: modes spécifiques qui ne doivent pas être aplatis en simple ISO natif (FX5 Dual Gain, ALEXA 35 Enhanced Sensitivity).

## V1.1
- Ajout des 4 caméras Blackmagic déjà présentes dans MEDIA.
- Ajout d'un bloc `media` dans les caméras disposant de presets d'enregistrement.
- FRAME continue de lire `sensorWidthMm`.
- DOF continue de lire `dof`.
- MEDIA lit maintenant `media.modes`.

## Mise à jour
Remplacer uniquement `cameras.json` dans le dépôt GitHub `BrunoSetTools/BOS-CAMERA-DB`.
Les applications gardent un fallback local et la dernière base récupérée pour fonctionner hors ligne.
