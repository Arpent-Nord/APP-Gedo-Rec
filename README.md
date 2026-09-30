# GEDO REC Rapport

Application web (installable sur iPhone / Android) qui produit le rapport de levé d'un relevé de voie fait au chariot Trimble GEDO CE avec GEDO Rec.

## Utilisation

1. Ouvrir l'application : https://renelangevin.github.io/GEDO-REC/
2. Sur iPhone : bouton Partager → **Sur l'écran d'accueil** pour l'installer (fonctionne ensuite hors ligne).
3. **Choisir les fichiers** : un `.sie` par voie levée (GEDO Office : axe, profil, dévers), l'export `.xml` (JobXML) du carnet GEDO Rec et, au besoin, le `.csv` des repères (nom,E,N,Z). Une clé USB-C apparaît dans l'app Fichiers, sous Emplacements.
4. **Lignes de levé** : pour chaque ligne du carnet, vérifier la voie associée (proposée automatiquement), le sens de marche (Auto = déduit de la position du prisme sur la voie, corrige un sens mal saisi au carnet), les points à exclure (ex. `29-30, 173`) ; décocher une ligne pour l'écarter. Les points suspects (écart marqué avec leurs voisins) sont proposés d'un toucher.
5. **Calculer les écarts** : un résultat par voie, avec **Rapport PDF** et **Tableau Excel**.

Tout le traitement se fait sur l'appareil : aucun fichier de levé n'est envoyé en ligne ni stocké dans ce dépôt.

## Calculs

- PK par projection sur l'axe de conception (alignements, arcs, clothoïdes) ; profil à raccordements paraboliques ; dévers interpolé.
- Prisme ramené au rail perpendiculairement au plan de roulement (hauteur = hauteur de cible + décalage vertical du côté fixe, lus dans le carnet, modifiables).
- Aller et retour moyennés sur une grille de 1 m ; décalage latéral aller/retour corrigé à parts égales.
- Rail directeur : rail bas en courbe, rail gauche ailleurs (modifiable).
- Conformité : plan et nivellement ±6 mm, taux de variation 1 mm / 2 m, écartement −1/+3 mm, dévers ±2 mm (modifiables), avec les seuils d'arrondi du rapport de référence.

## Fichiers

- `index.html` : l'application complète (aucune dépendance externe hormis les polices).
- `manifest.webmanifest`, `sw.js`, `icon-*.png` : installation et fonctionnement hors ligne.

## Publication

Settings → Pages → Source : *Deploy from a branch* → Branch `main`, dossier `/ (root)`.
