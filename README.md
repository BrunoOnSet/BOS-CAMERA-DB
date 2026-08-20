# BOS CAMERA DB V1.5

Mise à jour du 20 août 2026.

## Profils Blackmagic

Ajout des choix de rendu / Dynamic Range dans le bloc `exposure` des caméras Blackmagic :

- **Pocket Cinema Camera 4K** : Video / Extended Video / Film Gen 5 — Dual Native ISO 400 / 3200.
- **Pocket Cinema Camera 6K** : Video / Extended Video / Film Gen 5 — Dual Native ISO 400 / 3200.
- **URSA Mini Pro 12K** : Video / Extended Video / Film Gen 5 — ISO natif de référence 800.
- **URSA Mini Pro 4.6K G2** : Video / Extended Video / Film — ISO natif de référence 800. Le profil Film est conservé en **Gen 4** dans BOS, et n’est pas présenté comme Film Gen 5 natif.

## Principe de la DB

`Video`, `Extended Video` et `Film` décrivent le rendu / la plage dynamique. Ils ne créent pas de nouveaux ISO natifs. La propriété `profileSensitivityRelationship: "sharedNativeISO"` indique donc que les profils d’une même caméra partagent les mêmes sensibilités natives.

Le profil par défaut reste **Film Gen 5** pour Pocket 4K/6K et URSA 12K, et **Film** pour URSA Mini Pro 4.6K G2.

Toutes les données de la V1.4, dont le Sony α7S III, sont conservées.

## Sources Blackmagic

- Blackmagic Pocket Cinema Camera – manuel et documentation constructeur.
- Blackmagic URSA Mini – manuel et documentation constructeur.
