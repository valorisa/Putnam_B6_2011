# Putnam-B6-2011

## Auteur

[valorisa](https://www.github.com/valorisa)

---

## Problème

Soit \( p \) un nombre premier impair. Pour tout entier \( n \) de \( 0 \) à \( p-1 \), on considère la somme :
\
S(n) = \sum_{k=0}^{p-1} k! n^k
\

**Objectif :**  
Montrer que pour au moins \( \frac{p+1}{2} \) valeurs de \( n \), la somme \( S(n) \) n’est pas divisible par \( p \).

---

## Subtilité : « au plus » et « au moins »

- **Ce qu’on cherche à prouver** :  
  Pour **au moins** \( \frac{p+1}{2} \) valeurs de \( n \), \( S(n) \) **n’est pas divisible par** \( p \).
- **Ce qu’on démontre effectivement** :  
  Pour **au plus** \( \frac{p-1}{2} \) valeurs de \( n \), \( S(n) \) **est divisible par** \( p \).

**Pourquoi cette inversion ?**  
Il y a \( p \) valeurs possibles pour \( n \). Si au plus \( \frac{p-1}{2} \) valeurs de \( n \) annulent la somme, alors les autres, soit \( p - \frac{p-1}{2} = \frac{p+1}{2} \) valeurs, ne l’annulent pas.  
On passe de « au moins » à « au plus » grâce à ce complémentaire, ce qui est plus facile à démontrer en algèbre (bornes sur les racines d’un polynôme).

---

## Démonstration algébrique détaillée

### 1. Écriture de la condition

\
\sum_{k=0}^{p-1} k! n^k \equiv 0 \pmod{p}
\

### 2. Changement d’indice

\
\sum_{k=0}^{p-1} (p-1-k)! \, n^{p-1-k} \equiv 0 \pmod{p}
\

### 3. Décomposition du factoriel

\
(p-1-k)! = \frac{(p-1)!}{(p-k)(p-k+1)\cdots(p-1)}
\

d’où

\
\sum_{k=0}^{p-1} \frac{(p-1)!}{(p-k)(p-k+1)\cdots(p-1)} \cdot n^{p-1-k} \equiv 0 \pmod{p}
\

### 4. Théorème de Wilson

\
(p-1)! \equiv -1 \pmod{p}
\

donc

\
\sum_{k=0}^{p-1} \frac{-1}{(p-k)(p-k+1)\cdots(p-1)} \cdot n^{p-1-k} \equiv 0 \pmod{p}
\

### 5. Petit théorème de Fermat

Pour \( n \not\equiv 0 \),

\
n^{p-1} \equiv 1 \pmod{p} \implies n^{p-1-k} \equiv n^{-k} \pmod{p}
\

donc

\
\sum_{k=0}^{p-1} \frac{-1}{(p-k)(p-k+1)\cdots(p-1)} \cdot n^{-k} \equiv 0 \pmod{p}
\

### 6. Factorisation du signe

\
-\sum_{k=0}^{p-1} \frac{n^{-k}}{(p-k)(p-k+1)\cdots(p-1)} \equiv 0 \pmod{p}
\

### 7. Simplification du dénominateur

On utilise :

\
j \equiv -(p-j) \pmod{p}
\

pour tout \( j \) entre 1 et \( p-1 \).

Ainsi,

\
(p-k)(p-k+1)\cdots(p-1) \equiv (-k)(-k+1)\cdots(-1) = (-1)^k k! \pmod{p}
\

### 8. Forme finale

\
-\sum_{k=0}^{p-1} \frac{n^{-k}}{(-1)^k k!} \equiv 0 \pmod{p}
\

---

## Illustration de la chaîne d’équivalences

![Démonstration factorielle modulaire](img/Screenshot_2025-06-22-12-06-31-83_f9ee0578fe1cc94de7482bd41accb329.jpg)

À droite, on utilise la congruence pour chaque \( k \) :

\
1 \equiv -(p-1) \pmod{p}  
2 \equiv -(p-2) \pmod{p}  
\vdots  
k \equiv -(p-k) \pmod{p}
\

---

## Interprétation polynomiale et conclusion

En posant \( m = n^{-1} \) (l’inverse de \( n \) modulo \( p \)), la condition devient :

\
\sum_{k=0}^{p-1} \frac{m^k}{(-1)^k k!} \equiv 0 \pmod{p}
\

Ce polynôme de degré \( p-1 \) a la propriété que toutes ses racines non nulles sont **au moins doubles** (voir la vidéo ou la section mathématique pour la justification).  
Un polynôme de degré \( p-1 \) ne peut donc avoir plus de \( \frac{p-1}{2} \) racines distinctes.

**Conclusion :**
- \( S(n) \) est divisible par \( p \) pour **au plus** \( \frac{p-1}{2} \) valeurs de \( n \).
- Donc, pour **au moins** \( \frac{p+1}{2} \) valeurs de \( n \), \( S(n) \) **n’est pas divisible par** \( p \).

---

## Ressources

- [Vidéo explicative sur YouTube](https://youtu.be/DSp1rOl1jEo?si=VrI2m_0_M9PHf9Rz)
- [Théorème de Wilson (Wikipedia)](https://fr.wikipedia.org/wiki/Th%C3%A9or%C3%A8me_de_Wilson)
- [Petit théorème de Fermat (Wikipedia)](https://fr.wikipedia.org/wiki/Petit_th%C3%A9or%C3%A8me_de_Fermat)

---

## Licence

MIT

## Auteur

valorisa (2025)
