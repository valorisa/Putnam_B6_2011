# Putnam 2011 B6 — Analogie de l'horloge et des recettes

## Énoncé original

Soit `p` un nombre premier impair.

Montrer que, pour au moins `(p+1)/2` valeurs de `n` dans `[0, p-1]`, on a :

```text
p ne divise pas la somme, pour k allant de 0 à p-1, de k! * n^k
```

## Analogie de la vie courante

L'arithmétique modulo `p` se comporte comme une **horloge à p graduations**,
numérotées de `0` à `p-1`. Dès que le compteur atteint `p`, il revient à `0`,
exactement comme une aiguille qui boucle après un tour complet.

Imaginons `p` recettes de cuisine différentes, numérotées de `0` à `p-1`
selon la quantité de départ `n` d'un ingrédient de base. Pour chaque
recette `n`, on suit un protocole en `p` étapes numérotées `k = 0` à `p-1` :

- à l'étape `k`, on ajoute une dose égale à `k!` (k factorielle) multipliée
  par `n` puissance `k` ;
- on ne conserve jamais le total réel, seulement sa position sur l'horloge,
  c'est-à-dire son reste modulo `p`.

À la fin des `p` étapes, l'aiguille s'arrête sur l'une des `p` graduations.

## Ce que dit l'énoncé, en termes de l'analogie

Parmi les `p` recettes possibles, il en existe **au moins `(p+1)/2`** —
donc une majorité stricte — pour lesquelles l'aiguille de l'horloge ne
s'arrête jamais exactement sur minuit (la graduation `0`). Autrement dit,
pour ces recettes, le total accumulé n'est jamais un multiple exact de `p`,
quelle que soit la précision avec laquelle on dose les ingrédients.

## Correspondance terme à terme

| Objet mathématique | Élément de l'analogie |
| --- | --- |
| Nombre premier impair `p` | Nombre de graduations de l'horloge |
| Reste modulo `p` | Position de l'aiguille sur l'horloge |
| Valeur de `n` entre `0` et `p-1` | Recette de cuisine numérotée `n` |
| Somme des `k! * n^k` pour `k` de `0` à `p-1` | Total accumulé après les `p` étapes du protocole |
| `p` divise la somme | L'aiguille s'arrête exactement sur minuit (`0`) |
| `p` ne divise pas la somme | L'aiguille rate toujours le zéro de l'horloge |
| Au moins `(p+1)/2` valeurs de `n` conviennent | Une majorité stricte des recettes évite minuit |

## Exemple chiffré (p = 5, ingrédient générique)

Prenons `p = 5` et déroulons les 5 recettes correspondant à `n = 0, 1, 2, 3, 4`.

### Doses de base à chaque étape

| Étape `k` | `k!` | `k!` mod 5 |
| --- | --- | --- |
| 0 | 1 | 1 |
| 1 | 1 | 1 |
| 2 | 2 | 2 |
| 3 | 6 | 1 |
| 4 | 24 | 4 |

### Déroulé des 5 recettes

| Recette `n` | Étape 0 | Étape 1 | Étape 2 | Étape 3 | Étape 4 | Total mod 5 | Minuit atteint ? |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | 1 | 0 | 0 | 0 | 0 | 1 | Non |
| 1 | 1 | 1 | 2 | 1 | 4 | 4 | Non |
| 2 | 1 | 2 | 3 | 3 | 4 | 3 | Non |
| 3 | 1 | 3 | 3 | 2 | 4 | 3 | Non |
| 4 | 1 | 4 | 2 | 4 | 4 | 0 | Oui |

Sur les 5 recettes, une seule (`n = 4`) tombe exactement sur minuit. Les
4 autres (`n = 0, 1, 2, 3`) ratent systématiquement le zéro, soit largement
au-dessus du seuil minimal `(p+1)/2 = 3` garanti par l'énoncé.

## Exemple chiffré (p = 5, ingrédient = farine)

Reprenons `p = 5`, en fixant cette fois l'ingrédient de base à de la
**farine**, avec `n` exprimé en grammes (`n = 0, 1, 2, 3, 4` g). Les doses
de base `k!` mod 5 restent identiques à l'exemple précédent, seule la
lecture de `n` change.

Ici, on abandonne l'image de l'horloge au profit d'un repère plus culinaire :
le four est réglé sur un minuteur à `p` graduations, et lorsque le total
accumulé retombe pile sur `0` modulo `p`, cela signifie que le minuteur a
sonné au pire moment — **le gâteau brûle**. Tant que le total évite le `0`,
le gâteau sort du four à point, donc **le gâteau ne brûle pas**.

### Déroulé des 5 recettes (farine)

| Farine `n` (g) | Étape 0 | Étape 1 | Étape 2 | Étape 3 | Étape 4 | Total mod 5 | Le gâteau brûle ? |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 0 g | 1 | 0 | 0 | 0 | 0 | 1 | Non |
| 1 g | 1 | 1 | 2 | 1 | 4 | 4 | Non |
| 2 g | 1 | 2 | 3 | 3 | 4 | 3 | Non |
| 3 g | 1 | 3 | 3 | 2 | 4 | 3 | Non |
| 4 g | 1 | 4 | 2 | 4 | 4 | 0 | Oui |

Avec 4 g de farine, le total tombe pile sur un multiple de 5 : le minuteur
sonne au plus mauvais moment et **le gâteau brûle**. Pour les autres
grammages (0, 1, 2 et 3 g), le total ne tombe jamais sur un multiple de 5 —
**le gâteau ne brûle pas**, quelle que soit la précision du dosage à chaque
étape. Sur les 5 grammages testés, 4 recettes sur 5 donnent un gâteau qui
ne brûle pas, au-dessus du seuil minimal de 3 recettes réussies garanti
par l'énoncé pour `p = 5`.

Traduit intégralement dans ce vocabulaire, l'énoncé général affirme donc
que, pour au moins la moitié des grammages de farine testés, **le gâteau ne
brûle jamais**, quelle que soit la précision avec laquelle on suit le
protocole de dosage en `p` étapes.

## Note pédagogique

Cette analogie met en avant l'idée centrale du problème : les quantités
manipulées (les factorielles) croissent très vite, mais seule leur position
sur un cercle à `p` cases importe réellement. L'objectif de l'exercice est
alors de compter combien de « recettes de départ » évitent systématiquement
la case zéro de cette horloge modulaire.
