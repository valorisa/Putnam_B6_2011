# Putnam B6 2011 — Solution complète

## Le problème

Soit *p* un nombre premier impair. Pour tout entier *n* de 0 à *p* − 1, on considère la somme :

$$S(n) = \sum_{k=0}^{p-1} k! \cdot n^k$$

**Montrer** que pour au moins (*p* + 1)/2 valeurs de *n* dans {0, 1, 2,..., p-1}, la somme S(*n*) n'est **pas** divisible par *p*.

---

## Pourquoi ce problème est célèbre

Ce problème est l'un des plus difficiles jamais posés au concours Putnam. En 2011, **aucun des 3 407 candidats n'a obtenu le moindre point** : score collectif de 0/10 pour 100 % des participants.

La difficulté tient à une construction non naturelle — le polynôme auxiliaire G(*x*) = F(*x*) − *x* + *x*^*p* — qui exploite simultanément le petit théorème de Fermat, le théorème de Wilson et la théorie des racines multiples sur les corps finis.

---

## Contenu du repo

| Fichier | Description |
|---------|-------------|
| [putnam-b6-2011-solution.md](putnam-b6-2011-solution.md) | Solution complète en Markdown (LaTeX, étapes détaillées, remarques) |
| [putnam-b6-2011-solution.html](putnam-b6-2011-solution.html) | Version HTML autonome (rendu LaTeX via KaTeX, lisible dans un navigateur) |

---

## Plan de la démonstration

1. **Reformulation** — Traiter le cas *n* = 0, puis montrer que S(*n*) a au plus (*p* − 1)/2 racines dans {1, …, *p* − 1}
2. **Point de vue polynomial** — Interpréter S(*n*) comme un polynôme P(*x*) sur F_*p*
3. **Réduction à l'exponentielle tronquée** — Via Wilson, Fermat et un changement de variable, ramener l'étude à F(*x*) = ∑ *x*^*k* / *k*!
4. **Construction auxiliaire** — Définir G(*x*) = F(*x*) − *x* + *x*^*p* et montrer que G(*n*) ≡ F(*n*) et G'(*x*) ≡ F(*x*) (mod *p*)
5. **Racines doubles** — En déduire que toute racine de F est racine double de G, donc F a au plus (*p* − 1)/2 racines distinctes
6. **Conclusion** — Au moins (*p* + 1)/2 valeurs de *n* donnent *p* ∤ S(*n*). CQFD.

---

## Outils mathématiques utilisés

- Théorème de Wilson : (*p* − 1)! ≡ −1 (mod *p*)
- Petit théorème de Fermat : *n*^(*p*−1) ≡ 1 (mod *p*) pour *n* ≢ 0
- Théorie des polynômes sur les corps finis (multiplicité des racines)
- Isomorphismes du groupe multiplicatif F_*p*\*

---

## Borne améliorée (résultat ultérieur)

La borne (*p* − 1)/2 est grossière. En 2012, Sergey Stepanov a montré que le nombre de racines est majoré par 2 · *p*^(2/3), une borne beaucoup plus forte pour *p* grand. La borne optimale reste un **problème ouvert**.

---

## Source

Ce repo est basé sur la solution présentée par [Axel Arno](https://www.youtube.com/@axel_arno) dans sa vidéo :

- [Le problème où PERSONNE n'a trouvé UN SEUL point (Putnam B6 2011)](https://youtu.be/DSp1rOl1jEo)

## Ressources complémentaires

- [Putnam Archive — 2011 Problems](https://kskedlaya.org/putnam-archive/2011.pdf)
- [Théorème de Wilson — Wikipédia](https://fr.wikipedia.org/wiki/Th%C3%A9or%C3%A8me_de_Wilson)
- [Petit théorème de Fermat — Wikipédia](https://fr.wikipedia.org/wiki/Petit_th%C3%A9or%C3%A8me_de_Fermat)

---

## Licence

MIT
