# BASKET_SCOREBOARD.md — Spécifications v3.0 (pré-implémentation)

## 1. Objet
Créer une **v3.0** de l’application de tableau de score basket en respectant **au plus près la maquette visuelle fournie** (`basket-scoreboard-mockup.png`).

Cette phase est une **phase de cadrage** :
- extraction des spécifications visuelles et fonctionnelles ;
- extraction des assets image principaux ;
- identification des icônes pouvant être remplacées par une librairie d’icônes ;
- liste des questions à trancher avant l’implémentation.

---

## 2. Assets extraits depuis la maquette
Images de référence extraites directement depuis la maquette :

### 2.1. Header / branding
- `basketscore.png`
  - Contient le panier stylisé + le texte `BASKET SCORE` + les étoiles.
  - Usage prévu : référence visuelle principale du header.

### 2.2. Logos équipe bleue
- `bleulogo1.png` → loup bleu
- `bleulogo2.png` → félin/panthère bleue
- `bleulogo3.png` → requin bleu

### 2.3. Logos équipe rouge
- `redlogo1.png` → lion rouge
- `redlogo2.png` → renard rouge
- `redlogo3.png` → taureau rouge

### 2.4. Remarque importante
Ces PNG sont des **extractions de maquette** :
- ils contiennent l’éclairage / fond / contour observé dans la maquette ;
- ils ne sont pas des assets vectoriels de production ;
- ils peuvent servir :
  - soit comme **références**,
  - soit comme **assets temporaires**, 
  - soit comme base pour un re-découpage plus propre.

---

## 3. Structure visuelle globale observée
L’interface de la maquette est une **composition horizontale**, pensée pour un affichage **landscape** sur :
- iPad en mode paysage,
- ordinateur,
- télévision ou écran de salle.

### 3.1. Zones principales
1. **Barre haute flottante / header principal**
   - bouton menu en haut à gauche ;
   - bouton son / volume en haut à droite ;
   - branding centré (`BASKET SCORE`).

2. **Corps principal en 3 colonnes**
   - colonne gauche : équipe bleue ;
   - colonne centrale : chrono + commandes match ;
   - colonne droite : équipe rouge.

3. **Panneau d’aide / onboarding en bas**
   - bloc large, occupant toute la largeur ;
   - plusieurs cartes explicatives ;
   - bouton `FERMER` en bas à droite.

---

## 4. Spécifications de layout détaillées

### 4.1. Conteneur global
- fond général : noir très profond ;
- interface encapsulée dans un grand panneau aux coins fortement arrondis ;
- bordure lumineuse discrète gris / bleu nuit ;
- glow externe faible.

### 4.2. Hiérarchie visuelle
Priorité visuelle descendante :
1. scores des équipes ;
2. chrono ;
3. couleurs d’équipes et logos ;
4. boutons +1/+2/+3/-1 ;
5. panneau d’aide inférieur.

### 4.3. Répartition approximate des colonnes
- **gauche** ≈ 35 %
- **centre** ≈ 24 %
- **droite** ≈ 35 %
- marges internes relativement généreuses.

---

## 5. Identité visuelle

### 5.1. Palette dominante
#### Couleurs globales
- fond principal : noir / anthracite très sombre ;
- surfaces secondaires : gris graphite ;
- texte principal : blanc ;
- texte secondaire : gris clair.

#### Équipe bleue
- bleu saturé lumineux ;
- glow bleu néon ;
- boutons bleus avec dégradé vertical.

#### Équipe rouge
- rouge saturé lumineux ;
- glow rouge néon ;
- boutons rouges avec dégradé vertical.

#### Actions transverses
- `RESET` : jaune / or ;
- `ACTIVER` buzzer : rouge ;
- START : vert ;
- PAUSE : gris anthracite.

### 5.2. Effets graphiques
- bords arrondis très marqués ;
- halos lumineux externes ;
- légères bordures internes ;
- boutons avec effet glossy / profondeur ;
- look « scoreboard arcade / esport / broadcast ».

---

## 6. Typographie observée

### 6.1. Style général
- police **très condensée**, **très grasse**, **majuscules** ;
- lecture à grande distance prioritaire ;
- chiffres massifs pour les scores.

### 6.2. Pistes typographiques probables (à confirmer lors de l’implémentation)
- `Bebas Neue`
- `Anton`
- `Oswald`
- `Teko`
- police type `7-segment` / `digital` pour le chrono si souhaité

### 6.3. Application typographique par zone
- scores : très très gros, blanc, léger glow ;
- noms d’équipe : condensé, uppercase, couleur équipe ;
- labels (`CHRONO`, `BUZZER`, etc.) : uppercase, blanc ;
- aide : titres colorés, corps de texte blanc / gris.

---

## 7. Fonctionnalités visibles dans la maquette

### 7.1. Gestion des logos
Pour chaque équipe :
- 3 logos sélectionnables visibles en ligne ;
- un logo actif entouré / illuminé ;
- un bouton `CHANGER LES LOGOS` est aussi présent dans la zone basse gauche.

### 7.2. Gestion du score
Pour chaque équipe :
- affichage d’un score principal géant ;
- boutons :
  - `+1`
  - `+2`
  - `+3`
  - `-1`

### 7.3. Chrono de match
- bloc central `CHRONO` ;
- affichage numérique géant (format `MM:SS`) ;
- bouton `Play` ;
- bouton `Pause`.

### 7.4. Réglage du temps du chrono
Bloc dédié `TEMPS DU CHRONO` comportant :
- bouton `-`
- affichage du temps courant / temps de référence (ex. `05:00`)
- bouton `+`
- texte d’aide : `De 30 sec à 20 min`

### 7.5. Buzzer
- bloc `BUZZER`
- bouton principal `ACTIVER`
- icône de cloche / alerte
- comportement implicite attendu :
  - buzzer manuel ;
  - buzzer automatique en fin de chrono.

### 7.6. Reset
- grand bouton central `RESET`
- sous-texte : `TOUT REMETTRE À ZÉRO`

### 7.7. Nouveau match
- bouton en bas à droite `NOUVEAU MATCH`
- sémantiquement proche d’un reset complet avec nouvelle manche / nouvelle partie.

### 7.8. Aide embarquée
Bloc bas `COMMENT UTILISER L’APP` avec 5 cartes :
1. Changer les logos
2. Ajouter / retirer des points
3. Chrono & buzzer
4. Reset
5. Fonctionnalités

---

## 8. Texte visible dans la maquette (transcription utile)

### 8.1. Header
- `MENU`
- `BASKET SCORE`

### 8.2. Zone centrale
- `CHRONO`
- `TEMPS DU CHRONO`
- `De 30 sec à 20 min`
- `BUZZER`
- `ACTIVER`
- `RESET`
- `TOUT REMETTRE À ZÉRO`

### 8.3. Zones équipes
- `ÉQUIPE BLEUE`
- `ÉQUIPE ROUGE`
- `+1`, `+2`, `+3`, `-1`

### 8.4. Bas d’écran / aide
- `COMMENT UTILISER L’APP`
- `1. CHANGER LES LOGOS`
- `2. AJOUTER / RETIRER DES POINTS`
- `3. CHRONO & BUZZER`
- `4. RESET`
- `FONCTIONNALITÉS`
- `FERMER`
- `ASTUCE : Ajoute l’app à ton écran d’accueil pour y accéder en 1 clic !`

---

## 9. Comportement attendu pour la v3

### 9.1. Cibles supportées
- iPad paysage ;
- laptop / desktop ;
- TV / grand écran ;
- responsive horizontal prioritaire.

### 9.2. États d’interface à prévoir
- logo sélectionné / non sélectionné ;
- chrono en cours / pause ;
- plein écran actif / inactif ;
- mode TV actif / inactif ;
- aide ouverte / fermée ;
- buzzer activé / disponible.

### 9.3. Effets demandés / déjà voulus dans les versions précédentes
À conserver si possible dans le style de la maquette :
- flash lumineux lors de l’ajout d’un point ;
- buzzer automatique en fin de chrono ;
- buzzer manuel ;
- sauvegarde locale ;
- plein écran.

---

## 10. Assets à conserver comme fichiers image
L’utilisateur a explicitement demandé de préparer / sauvegarder :
- `basketscore.png`
- `bleulogo1.png`
- `bleulogo2.png`
- `bleulogo3.png`
- `redlogo1.png`
- `redlogo2.png`
- `redlogo3.png`

---

## 11. Icônes pouvant être remplacées par une librairie d’icônes
Les éléments suivants peuvent probablement être remplacés par une librairie standard (`Lucide`, `Font Awesome`, `Material Symbols`, etc.) :

- menu / hamburger → `menu`
- volume / haut-parleur → `volume-2`, `volume-high`
- play → `play`
- pause → `pause`
- plus → `plus`
- moins → `minus`
- cloche / alerte buzzer → `bell`, `bell-ring`
- reset / rotation → `rotate-ccw`, `refresh-cw`, `arrows-rotate`
- trophée → `trophy`
- fermeture → `x`, `xmark`
- éclair / ampoule / effet → `sparkles`, `lightbulb`
- horloge → `clock-3`, `timer`
- plein écran → `maximize`, `expand`

### Recommandation
Pour la v3, utiliser des **icônes vectorielles** via une librairie plutôt que des images bitmap pour tous les pictogrammes UI, sauf :
- branding `BASKET SCORE` si on veut coller exactement à la maquette ;
- logos d’animaux si on conserve le style illustré.

---

## 12. Points d’écart potentiels entre maquette et implémentation
À arbitrer avant développement :
1. faut-il reproduire la maquette **pixel-perfect** ou **très proche mais plus simple** ?
2. les PNG extraits doivent-ils être utilisés directement ou uniquement comme références ?
3. le branding `BASKET SCORE` doit-il rester une image (`basketscore.png`) ou être entièrement refait en HTML/CSS ?
4. le panneau d’aide du bas doit-il être :
   - toujours affiché,
   - repliable,
   - ou modal ?
5. le bouton `ACTIVER` buzzer doit-il :
   - jouer un buzzer immédiatement,
   - activer le buzzer automatique,
   - ou faire les deux ?
6. le bouton `NOUVEAU MATCH` doit-il :
   - remettre tout à zéro,
   - remettre à zéro mais conserver les logos,
   - ou relancer une configuration initiale complète ?
7. faut-il conserver le mode TV de la v2.3 dans la v3 ?

---

## 13. Proposition d’architecture v3 (préliminaire)
### 13.1. Technologies
- HTML / CSS / JS vanilla, ou React si souhaité
- CSS avec variables de thème
- stockage local `localStorage`
- icônes SVG / librairie d’icônes

### 13.2. Découpage probable des composants
- `TopBar`
- `BrandHeader`
- `TeamPanelBlue`
- `TeamPanelRed`
- `CentralControlPanel`
- `HelpPanel`
- `Modal / Confirm`

---

## 14. Questions à trancher avant implémentation v3
1. **Souhaites-tu une reproduction visuelle quasi exacte de la maquette, ou une version fidèle mais allégée techniquement ?**
2. **Le panneau d’aide du bas doit-il être ouvert par défaut comme sur la maquette, ou masqué/repliable ?**
3. **Le bouton `ACTIVER` du buzzer doit-il être interprété comme un buzzer manuel immédiat, ou comme un interrupteur ON/OFF du buzzer automatique ?**
4. **Le bouton `NOUVEAU MATCH` doit-il conserver les logos / noms d’équipe, ou tout remettre par défaut ?**
5. **Pour le branding central, veux-tu utiliser `basketscore.png` tel quel, ou préfères-tu que je refasse le header en HTML/CSS + icône panier ?**
6. **Veux-tu que la v3 conserve le mode TV / plein écran de la v2.3 ?**
7. **Souhaites-tu garder le flash lumineux sur panier marqué dans la v3, même si la maquette ne le montre pas explicitement comme animation ?**

---

## 15. Version
- Cette phase de spécification correspond à : **v3.0 — cadrage / extraction / préparation**
- La prochaine phase sera : **implémentation v3.x** après validation des assets et réponses aux questions.
