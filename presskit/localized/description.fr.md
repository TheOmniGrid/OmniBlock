# OmniBlock — Fiche boutique (Français)

Copie traduite pour les fiches françaises du Chrome Web Store et d'AMO.
Les deux boutiques acceptent des fiches par langue -- voir
`submission-runbook.md` pour savoir où saisir chaque texte. La structure,
les limites de caractères, la catégorie, les captures d'écran, les
visuels promotionnels et la déclaration de collecte de données restent
dans `listing.md` (en anglais, source de vérité pour le processus) --
ce fichier ne contient que le texte destiné aux utilisateurs, réellement
saisi par langue.

## Nom

```
OmniBlock
```

## Description courte (Chrome Web Store, ≤132 caractères)

123 caractères :

```
Bloqueur de pubs, traceurs et menaces : 6 niveaux de protection, Security Shield, listes personnalisées, réglages par site.
```

## Résumé (AMO, ≤250 caractères)

227 caractères :

```
Bloque les publicités, traceurs et sites malveillants connus sur 6 niveaux de protection, plus un Security Shield indépendant. Listes personnalisées, confiance par site, sélecteur d'éléments. Zéro télémétrie, entièrement local.
```

## Description complète (les deux boutiques)

```
OmniBlock est un bloqueur de contenu multi-navigateur : publicités,
traceurs, bannières de cookies et sites malveillants connus, avec un
curseur de protection de 0 à 5, un Security Shield indépendant et
toujours actif, des réglages par site, des abonnements à des listes de
filtres personnalisées, et un sélecteur d'éléments au clic.

HONNÊTES SUR LES DIFFÉRENCES ENTRE PLATEFORMES

Sur Chrome, Edge, Brave et les autres navigateurs basés sur Chromium,
OmniBlock fonctionne sur l'API native declarativeNetRequest de Manifest
V3. Aucune extension Manifest V3 -- OmniBlock compris -- ne peut égaler ce
que faisait uBlock Origin à l'époque de MV2, car Chrome a supprimé l'API
de filtrage dynamique qui le permettait. Sur Chromium, la vraie
concurrence d'OmniBlock, ce sont uBO Lite et ABP-MV3, et notre objectif
est de les surpasser en profondeur de listes de filtres, en ergonomie des
niveaux de protection et en réglages par site, tout en tournant à la
vitesse native de DNR : zéro JavaScript dans le chemin des requêtes, ce
qui est strictement plus rapide que toute correspondance évaluée en JS
d'un bloqueur de l'ère MV2.

Sur Firefox, OmniBlock utilise webRequest en mode blocage complet avec son
propre moteur de filtrage, ce qui le place vraiment dans la même
catégorie qu'uBlock Origin : prise en charge complète de la syntaxe des
listes de filtres, règles illimitées, et un moteur de correspondance qui,
selon les propres benchmarks publiés par Ghostery, est plus rapide que
celui d'uBO.

Nous préférons vous le dire d'emblée plutôt que de vous laisser le
découvrir par vous-même.

FONCTIONNALITÉS

- 6 niveaux de protection (de Désactivé à Forteresse), chacun cumulatif
  et précompilé -- changer de niveau est instantané, sans redémarrage
- Security Shield indépendant : listes de renseignement sur les menaces
  (malwares, hameçonnage, fraude, faux magasins) qui restent actives
  même au niveau de protection Désactivé, car la sécurité n'est pas une
  préférence de blocage publicitaire
- Abonnements à des listes de filtres personnalisées -- abonnez-vous à
  n'importe quelle URL de liste en syntaxe adblock ou hosts
- Mes filtres -- rédigez vos propres règles de filtrage à la main,
  validées ligne par ligne
- Sélecteur d'éléments -- cliquez pour masquer tout ce qu'une liste de
  filtres aurait manqué
- Réglages par site -- faites entièrement confiance à un site en un
  clic pour l'exempter du blocage
- Tableau de bord statistique local -- historique des requêtes bloquées
  et domaines les plus bloqués (Firefox ; voir la note de la page
  Statistiques expliquant pourquoi Chromium ne peut exposer ces données
  à aucune extension)
- Importez/exportez vos réglages sous forme d'un seul fichier
- Interface Rift exclusivement sombre (système de design OmniVex, le
  bleu caractéristique d'OmniBlock) conçue pour un popup rapide et sans
  friction

CONFIDENTIALITÉ

Aucune collecte de données. Pas de télémétrie, pas d'analytique, pas de
comptes, pas de serveur. Les listes de filtres sont récupérées sous
forme de texte en syntaxe adblock auprès de leurs mainteneurs publics
(EasyList, les listes de filtres d'uBlock Origin, les listes de blocage
DNS de HaGeZi). La bibliothèque de scriptlets que ces règles peuvent
référencer est embarquée directement dans l'extension, figée à une
version précise et vérifiée -- et toute liste à laquelle vous vous
abonnez vous-même voit ses lignes invoquant des scriptlets supprimées
avant même que les moteurs de blocage d'OmniBlock ne les voient.
Politique complète : voir l'onglet Confidentialité de cette fiche.
```
