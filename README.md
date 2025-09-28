# Putnam_B6_2011

## Problème

Soit \( p \) un nombre premier impair. Pour tout entier \( n \) de 0 à \( p-1 \), on considère la somme :
```
S(n) = ∑_{k=0}^{p-1} k!*n^k
```

**Objectif :** Montrer que pour au moins \( (p+1)/2 \) valeurs de \( n \), la somme \( S(n) \) n’est pas divisible par \( p \).

## Subtilité : « au plus » et « au moins »

- Ce qu’on cherche à prouver : Pour au moins \( (p+1)/2 \) valeurs de \( n \), \( S(n) \) n’est pas divisible par \( p \).
- Ce qu’on démontre effectivement : Pour au plus \( (p-1)/2 \) valeurs de \( n \), \( S(n) \) est divisible par \( p \).

## Démonstration algébrique détaillée

### 1. Écriture de la condition
```
∑_{k=0}^{p-1} k! n^k ≡ 0 (mod p)
```

### 2. Changement d’indice
```
∑_{k=0}^{p-1} (p-1-k)! n^{p-1-k} ≡ 0 (mod p)
```

### 3. Décomposition du factoriel
```
(p-1-k)! = (p-1)! / (p-k)(p-k+1)...(p-1)
```

### 4. Théorème de Wilson
```
(p-1)! ≡ -1 (mod p)
```

### 5. Petit théorème de Fermat
Pour \( n \neq 0 \) :
```
n^{p-1} ≡ 1 (mod p)
n^{p-1-k} ≡ n^{-k} (mod p)
```

### 6. Factorisation du signe
```
-∑_{k=0}^{p-1} [n^{-k} / (p-k)...(p-1)] ≡ 0 (mod p)
```

### 7. Simplification du dénominateur
On utilise :
```
j ≡ -(p-j) (mod p)
```
pour tout \( j \) de 1 à \( p-1 \).

Ainsi :
```
(p-k)...(p-1) ≡ (-k)...(-1) = (-1)^k k! (mod p)
```

### 8. Forme finale
```
-∑_{k=0}^{p-1} [n^{-k}/((-1)^k k!)] ≡ 0 (mod p)
```

## Interprétation polynomiale et conclusion

En posant \( m = n^{-1} \) (l’inverse de \( n \) modulo \( p \)), la condition devient :
```
∑_{k=0}^{p-1} [m^k / ((-1)^k k!)] ≡ 0 (mod p)
```
Ce polynôme de degré \( p-1 \) a toutes les racines non nulles au moins doubles, donc au plus \( (p-1)/2 \) racines distinctes.

**Conclusion :**
- \( S(n) \) est divisible par \( p \) pour au plus \( (p-1)/2 \) valeurs de \( n \).
- Pour au moins \( (p+1)/2 \) valeurs, \( S(n) \) n’est pas divisible par \( p \).

## Ressources
- Vidéo explicative sur YouTube
- Théorème de Wilson (Wikipedia)
- Petit théorème de Fermat (Wikipedia)

## Licence
MIT

Citations :
[1] 1000020631.jpg https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/images/40251661/2bf8eb5f-a053-4c0a-9e95-f94ed2baab79/1000020631.jpg
