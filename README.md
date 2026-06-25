# Basket Scoreboard

Mini application web de tableau de score basket, pensée pour un usage simple sur **iPad**, **ordinateur** ou **TV** via GitHub Pages.

La version courante est **v3.8**.

---

## Objectif

Cette application permet d’afficher et de piloter un tableau de score pour un match de basket entre deux équipes.

Elle est conçue pour être :

- lisible à distance ;
- utilisable par des enfants ou un adulte sans formation ;
- compatible iPad / ordinateur / TV ;
- hébergeable très simplement avec GitHub Pages ;
- autonome côté client, sans serveur et sans base de données.

---

## Fonctionnalités principales

### Score

- Deux équipes : **Équipe Bleue** et **Équipe Rouge**.
- Noms d’équipes modifiables directement dans l’interface.
- Sauvegarde locale automatique des noms.
- Boutons de score :
  - `+1`
  - `+2`
  - `+3`
  - `-1`
- Effet flash visuel lors d’un changement de score.

### Chrono

- Chronomètre principal au format `MM:SS`.
- Bouton `Play`.
- Bouton `Pause`.
- Réglage du temps par boutons `-` et `+`.
- Saisie directe du temps au format `MM:SS`.
- Temps autorisé : de **30 secondes** à **20 minutes**.
- Sauvegarde locale automatique du temps configuré.

### Buzzer

- Buzzer automatique de fin de chrono.
- Bouton `ACTIVER / ACTIVÉ` pour activer ou désactiver le buzzer de fin de chrono.
- Son de buzzer long et aigu, de type `THEUUUUU`, d’environ 4 secondes.
- Bouton son global en haut à droite pour activer ou couper les sons de l’application.

### Logos

- Trois logos sélectionnables pour l’équipe bleue.
- Trois logos sélectionnables pour l’équipe rouge.
- Logo sélectionné mis en évidence par un contour et un halo.
- Logos non sélectionnés atténués.
- Sauvegarde locale automatique du logo sélectionné.

### Modes d’affichage

- Mode standard pour iPad / ordinateur.
- Mode TV pour affichage grand écran.
- Bouton plein écran.
- Interface responsive.

### Menu / aide

Le bouton `MENU` ouvre une section d’aide intégrée contenant :

- explication des logos ;
- explication des points ;
- explication du chrono et du buzzer ;
- explication du reset ;
- liste des fonctionnalités ;
- liste des versions disponibles.

---

## Versions disponibles

Les versions historiques peuvent être exposées dans le menu de l’application si les fichiers correspondants sont présents dans le projet :

```html
<ul>
  <li><a href="v2.1.html">v2.1</a></li>
  <li><a href="v2.3.html">v2.3</a></li>
  <li><a href="v3.1.html">v3.1</a></li>
  <li><a href="v3.2.html">v3.2</a></li>
  <li><a href="v3.3.html">v3.3</a></li>
</ul>
```

---

## Structure recommandée du dépôt

```text
.
├── index.html
├── v2.1.html
├── v2.3.html
├── v3.1.html
├── v3.2.html
├── v3.3.html
├── README.md
└── img/
    ├── bascketscore.png
    ├── basketscore.png
    ├── bleulogo1.png
    ├── bleulogo2.png
    ├── bleulogo3.png
    ├── redlogo1.png
    ├── redlogo2.png
    └── redlogo3.png
```

> Remarque : l’application utilise prioritairement `img/bascketscore.png` pour le logo du titre, avec un fallback possible vers `img/basketscore.png` selon les versions.

---

## Installation locale

Aucune installation n’est nécessaire.

Il suffit d’ouvrir le fichier HTML dans un navigateur moderne :

```text
index.html
```

Pour éviter certaines restrictions liées aux navigateurs, notamment sur les sons, il est préférable de servir le dossier via un petit serveur local :

```bash
python3 -m http.server 8080
```

Puis ouvrir :

```text
http://localhost:8080
```

---

## Déploiement GitHub Pages

### 1. Créer le dépôt GitHub

Créer un dépôt, par exemple :

```text
basket-scoreboard
```

### 2. Ajouter les fichiers

Ajouter au dépôt :

- `index.html`
- `README.md`
- le dossier `img/`
- éventuellement les anciennes versions `v2.1.html`, `v2.3.html`, `v3.1.html`, etc.

### 3. Activer GitHub Pages

Dans GitHub :

1. ouvrir le dépôt ;
2. aller dans **Settings** ;
3. ouvrir **Pages** ;
4. choisir :
   - Source : `Deploy from a branch`
   - Branch : `main`
   - Folder : `/ (root)`
5. sauvegarder.

L’application sera disponible à une URL du type :

```text
https://<utilisateur>.github.io/<nom-du-repo>/
```

---

## Utilisation sur iPad

1. Ouvrir l’URL GitHub Pages dans **Safari**.
2. Appuyer sur le bouton de partage.
3. Choisir **Ajouter à l’écran d’accueil**.
4. Lancer ensuite l’application depuis l’icône créée.

Cela donne une expérience proche d’une application plein écran.

---

## Utilisation sur TV

### Avec un ordinateur connecté à la TV

1. Ouvrir l’application dans un navigateur.
2. Cliquer sur **Mode TV**.
3. Cliquer sur **Plein écran**.

### Avec le navigateur intégré d’une TV

1. Ouvrir l’URL GitHub Pages.
2. Activer **Mode TV**.
3. Activer le plein écran si le navigateur le permet.

---

## Raccourcis clavier

Les raccourcis sont actifs uniquement lorsque l’utilisateur n’est pas en train d’éditer un champ texte.

| Touche | Action |
|---|---|
| `Espace` | Play / Pause |
| `F` | Plein écran |
| `M` | Mute / Unmute global |
| `B` | Activation / désactivation du buzzer de fin |
| `T` | Mode TV |
| `Échap` | Fermer le menu si ouvert |

---

## Stockage local

L’application utilise `localStorage` pour mémoriser localement :

- noms des équipes ;
- scores ;
- logos sélectionnés ;
- temps du chrono ;
- activation du buzzer ;
- mode TV ;
- état du menu.

Les données sont stockées uniquement dans le navigateur de l’appareil utilisé.

---

## Assets attendus

Les images doivent être placées dans le dossier `img/`.

### Titre

```text
img/bascketscore.png
img/basketscore.png
```

### Équipe bleue

```text
img/bleulogo1.png
img/bleulogo2.png
img/bleulogo3.png
```

### Équipe rouge

```text
img/redlogo1.png
img/redlogo2.png
img/redlogo3.png
```

---

## Dépendances externes

L’application charge des polices et icônes depuis Google Fonts :

- `Anton`
- `Bebas Neue`
- `Orbitron`
- `Material Symbols Rounded`

Si l’application doit fonctionner totalement hors ligne, il faudra héberger localement ces polices ou remplacer les `@import` / liens Google Fonts par des fichiers locaux.

---

## Mise à jour de l’application

Pour publier une nouvelle version :

1. modifier le fichier HTML ;
2. mettre à jour le numéro de version affiché dans le menu ;
3. éventuellement sauvegarder l’ancienne version sous un nom comme `v3.8.html` ;
4. remplacer `index.html` par la nouvelle version ;
5. commit / push vers GitHub.

Exemple :

```bash
git add index.html README.md img/
git commit -m "Update basket scoreboard"
git push
```

GitHub Pages redéploie automatiquement après le push.

---

## Notes de conception

- L’interface privilégie la lisibilité à distance.
- Les gros chiffres utilisent une police de type scoreboard.
- Les boutons principaux sont volontairement larges pour une utilisation tactile.
- Les sons peuvent nécessiter une première interaction utilisateur sur iPad / Safari avant d’être autorisés par le navigateur.
- Le bouton **ACTIVER** contrôle le buzzer de fin de chrono.
- Le bouton son en haut à droite coupe ou réactive tous les sons.

---

## Licence

Projet personnel / familial.

À compléter selon le mode de diffusion souhaité.
