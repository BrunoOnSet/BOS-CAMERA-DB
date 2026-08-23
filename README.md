BOS_CAMERA_DB V1.7
====================

Mise à jour : 2026-08-23

Objectif de cette version
-------------------------
Rendre les données d'exposition exploitables par BOS EXPO aussi rigoureuses que possible,
avec une règle simple :

- la courbe Log / le rendu est une chose ;
- la dynamique réelle du capteur est une autre chose ;
- aucune valeur capteur manquante n'est inventée ou déduite si le constructeur ne la publie pas.

Politique de données
--------------------
1. `waveformGuide`
   Décrit la relation signal <-> exposition de la courbe ou du rendu.
   Un nombre de traits dans cette table ne doit JAMAIS être lu comme la dynamique totale de la caméra.

2. `dynamicRangeReference`
   Décrit uniquement une dynamique / latitude publiée par le constructeur.
   Quand une répartition sous / au-dessus du gris est disponible, elle est liée à l'ISO/EI de base indiqué.

3. Aucune extrapolation capteur
   Si Sony publie « 15+ stops » mais ne donne pas la latitude basse, la base ne calcule PAS
   automatiquement « 9+ stops sous le gris » à partir d'un repère +6.

4. Tables dérivées
   Une `stopTable` peut être calculée à partir d'une formule constructeur ou d'une LUT constructeur
   identifiée. Elle reste alors une table de COURBE, pas une mesure de dynamique capteur.

Sony S-Log3
-----------
Ajout d'un `waveformGuide` commun aux profils S-Log3 à partir de la formule officielle Sony.

Repères principaux :
- gris 18 % : 40,64 % calculé, publié par Sony comme ≈41 %
- blanc 90 % : ≈61 %
- +6 stops / gris : 93,87 %

La `stopTable` va de -8 à +6 uniquement comme plage de lecture de courbe.
Elle ne définit pas le plancher de bruit du capteur.

Références de dynamique ajoutées :
- FX30 : 14+ stops constructeur
- FX3 : 15+ stops constructeur
- FX5 : 15+ stops constructeur
- FX6 : 15+ stops constructeur

Quand Sony publie explicitement `6.0E` à l'EI égal à la Base ISO, ce repère est stocké :
- FX30 : 800 / 2500
- FX3 : 800 / 12800
- FX5 : 800 / 4000 / 12800

Pour FX6, aucune répartition haute/basse n'a été ajoutée sans source explicite correspondante.

ARRI
----
ALEXA Mini LF / LogC3 :
- référence EI 800
- dynamique constructeur : 14,5 stops
- 6,9 stops sous le gris
- 7,6 stops au-dessus du gris
- gris LogC3 : 39,10 %
- stopTable : valeurs constructeur ARRI, Table 5

ALEXA 35 / LogC4 :
- référence EI 800
- dynamique constructeur : 17,0 stops
- 7,7 stops sous le gris
- 9,3 stops au-dessus du gris
- gris LogC4 : 27,84 %
- stopTable : formule LogC4 officielle
- la courbe LogC4 elle-même est indépendante de l'EI

Blackmagic
----------
Les données V1.6 sont conservées :
- Film Gen 5 : fonction de transfert publique
- Video / Extended Video : LUT constructeur
- URSA Mini Pro 4.6K G2 / Gen 4 : repères historiques toujours marqués approximatifs

Aucune nouvelle dynamique capteur Blackmagic n'a été ajoutée dans cette version si elle n'était
pas déjà structurée de manière suffisamment certaine dans la base.

Sources constructeur principales
--------------------------------
Sony S-Log3 Technical Summary :
https://download.pro.sony/FNGP/protein/1237494271390/1237494271406.pdf

Sony Help Guide for Creators :
https://helpguide.sony.net/di/pp/v1/en/contents/TP0000909109.html

ARRI Dynamic Range White Paper :
https://www.arri.com/resource/blob/295460/e10ff8a5b3abf26c33f8754379b57442/2022-09-28-arri-dynamic-range-whitepaper-data.pdf

ARRI LogC3 :
https://www.arri.com/resource/blob/31918/66f56e6abb6e5b6553929edf9aa7483e/2017-03-alexa-logc-curve-in-vfx-data.pdf

ARRI LogC4 :
https://www.arri.com/resource/blob/278790/bea879ac0d041a925bed27a096ab3ec2/2022-05-arri-logc4-specification-data.pdf
