# BOS CAMERA DB V1.3

Mise à jour du 18 août 2026.

## Correction S-Cinetone

- Sony FX30 : repères S-Cinetone 125 / 400 ISO. ISO 125 est le réglage ISO par défaut documenté par Sony ; 400 est conservé comme repère de bascule haute sensibilité BOS/EXPO.
- Sony FX3 : repères S-Cinetone 100 / 2000 ISO. ISO 100 est le réglage ISO par défaut documenté par Sony ; 2000 est conservé comme repère de bascule haute sensibilité BOS/EXPO.
- Sony FX6 : Base Sensitivity S-Cinetone documentées par Sony : Low 320 / High 5000 ISO.
- Sony FX5 : Base Sensitivity S-Cinetone documentées par Sony : Low 320 / Mid 1600 / High 5000 ISO, plus Low Dual Gain à ISO 320.

Les valeurs S-Cinetone ne sont pas assimilées automatiquement aux Base ISO Cine EI S-Log3. Le champ `baseType` indique leur nature.

Toutes les autres données V1.2 (DOF, MEDIA, exposition ARRI/RED/Blackmagic, etc.) sont conservées.
