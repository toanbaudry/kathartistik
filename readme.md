#!/usr/bin/env python3
# -*- coding: utf-8 -*-
"""
Created on Wed Nov 25 10:30:53 2026

@author: toanb
"""

# Kathartistik — le site

## Ce qu'il y a dans le dossier

```
index.html             le site (tu n'as pas besoin d'y toucher)
numeros.json           la liste des numéros
numeros/01/            les pages du numéro 01 (p1.png … p8.png, poster.png)
images/                le logo
mentions-legales.html  à compléter avant la mise en ligne
lib/                   (facultatif) copie locale de Three.js
```

## Mettre le site en ligne (5 minutes)

1. Complète `mentions-legales.html` (les passages surlignés).
2. Va sur https://app.netlify.com/drop et crée un compte gratuit.
3. Glisse le dossier `kathartistik` entier sur la page.
4. Netlify te donne un lien public (du type `xxx.netlify.app`). Dans « Site configuration », tu peux changer ce nom ou relier ton propre domaine (ex. kathartistik.fr, ~10 €/an chez OVH ou Gandi).

Pour une mise à jour, re-glisse le dossier sur l'onglet « Deploys » de ton site.

## Mises à jour automatiques (recommandé ensuite)

1. Crée un compte sur https://github.com, puis un dépôt « kathartistik ».
2. « Add file → Upload files » : glisse le contenu du dossier.
3. Sur Netlify : « Add new site → Import an existing project → GitHub », choisis le dépôt.

Ensuite, chaque fichier ajouté ou modifié sur GitHub met le site à jour tout seul en une minute.

## Publier un nouveau numéro

1. Dans Figma : une frame par page, 595 × 842, nommées p1 (couverture) à p8 (4e).
   Export PNG 2x (ou JPG qualité 85 pour alléger). Toutes les pages à l'endroit.
   Affiche numérique (facultatif) : frame 1190 × 1684 nommée poster.
2. Crée le dossier `numeros/02/` et mets-y les fichiers.
3. Dans `numeros.json`, ajoute un bloc à la fin de la liste :

```json
    ,{
      "numero": "02",
      "oeuvre": "Titre de la BD",
      "auteur": "Auteur·ice, année",
      "date": "printemps 2027",
      "prix": "3 €",
      "papier": "#ffe45a",
      "papier2": "#f2c94c",
      "affiche": "imprime",
      "dossier": "numeros/02/"
    }
```

- `papier` : couleur du papier (utilisée tant qu'une page manque).
- `affiche` : `"imprime"` (affiche = les 4 panneaux) ou `"numerique"` (affiche pleine page, fichier poster.png).

Le dernier numéro de la liste s'ouvre par défaut ; un menu en haut à droite permet de revenir aux anciens.
Lien direct vers un numéro : `ton-site/?n=01`.

## Three.js en local (facultatif)

Le site charge la 3D depuis un serveur public (unpkg). Pour ne dépendre de personne, télécharge
https://unpkg.com/three@0.180.0/build/three.module.js et place-le dans `lib/three.module.js`.
