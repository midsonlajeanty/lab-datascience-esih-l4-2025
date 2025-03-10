# Rappel sur les Collections Python et Fonctions Utiles

#### Objectifs :
- Comprendre et manipuler les collections fondamentales en Python : **listes, tuples, dictionnaires et ensembles**.
- Appliquer des fonctions avancées (`map`, `filter`, `sorted`, `reduce`) pour le traitement des données.
- Lire et écrire des fichiers en Python.

---

## 1. Les Collections en Python
Python propose quatre principales structures de données intégrées pour stocker des collections de données :

| Type         | Mutable ? | Indexé ? | Duplicats autorisés ? | Exemple |
|-------------|----------|----------|---------------------|---------|
| **Liste** (`list`) | ✅ Oui | ✅ Oui | ✅ Oui | `[1, 2, 3, 4]` |
| **Tuple** (`tuple`) | ❌ Non | ✅ Oui | ✅ Oui | `(1, 2, 3, 4)` |
| **Dictionnaire** (`dict`) | ✅ Oui | ❌ Non | ❌ Non (clés uniques) | `{"nom": "Alice", "âge": 25}` |
| **Ensemble** (`set`) | ✅ Oui | ❌ Non | ❌ Non | `{1, 2, 3, 4}` |

---

### 1.1 Listes (`list`)
Une liste est une structure **ordonnée et modifiable**. Elle permet de stocker des éléments de types variés.

```python
# Définition d'une liste
fruits = ["pomme", "banane", "orange"]
print(fruits[0])  # Accès au premier élément

# Ajout d'un élément
fruits.append("mangue")

# Suppression d'un élément
fruits.remove("banane")

# Itération sur une liste
for fruit in fruits:
    print(fruit)
```

#### Méthodes utiles sur les listes
```python
nombres = [10, 20, 30, 40]

nombres.append(50)  # Ajoute 50 à la fin
nombres.pop()  # Supprime le dernier élément
nombres.index(30)  # Renvoie l'index de 30
nombres.sort(reverse=True)  # Trie en ordre décroissant
nombres.reverse()  # Inverse l'ordre des éléments
nombres.insert(1, 25)  # Insère 25 à l'index 1
nombres.remove(30)  # Supprime la première occurrence de 30
nombres.count(20)  # Compte le nombre d'occurrences de 20
nombres.clear()  # Supprime tous les éléments

print(nombres)  # []
```

---

### 1.2 Tuples (`tuple`)
Un **tuple** est **immuable** et permet un accès rapide aux éléments.

```python
coordonnees = (12.4, 45.6)
print(coordonnees[0])  # 12.4

# Déballage de tuple
x, y = coordonnees
print(x, y)  # 12.4 45.6
```

---

### 1.3 Dictionnaires (`dict`)
Un dictionnaire stocke des **paires clé-valeur** et est **rapide** pour la recherche.

```python
personne = {"nom": "Alice", "age": 25}

# Accès aux valeurs
print(personne["nom"])  # Alice

# Ajout d’une nouvelle clé
personne["ville"] = "Paris"

personne["age"] = 26  # Modification de la valeur

personne.pop("ville")  # Suppression d'une clé et renvoie la valeur
personne.clear()  # Supprime tous les éléments
permettent.keys()  # Renvoie les clés
personne.values()  # Renvoie les valeurs
personne.clear()  # Supprime tous les éléments

del personne["age"]  # Suppression d'une clé


# Itération sur les clés et valeurs
for cle, valeur in personne.items():
    print(f"{cle}: {valeur}")
```

---

### 1.4 Ensembles (`set`)
Les ensembles stockent des éléments **uniques** et sont optimisés pour les opérations ensemblistes.

```python
nombres = {1, 2, 3, 4, 4}  # Doublons supprimés automatiquement

nombres.add(5)
nombres.remove(1)

print(nombres)  # {2, 3, 4, 5}
```

#### Opérations d’ensembles
```python
a = {1, 2, 3}
b = {3, 4, 5}

print(a | b)  # Union {1, 2, 3, 4, 5} ou `a.union(b)`
print(a & b)  # Intersection {3} ou `a.intersection(b)`
print(a - b)  # Différence {1, 2} ou `a.difference(b)`
print(a ^ b)  # Différence symétrique {1, 2, 4, 5} ou `a.symmetric_difference(b)`
```

---

## 2. Fonctions Avancées : `map`, `filter`, `sorted`, `reduce`

Ces fonctions permettent un **traitement fonctionnel des données**.

### 2.1 `map()` - Appliquer une fonction à chaque élément
```python
nombres = [1, 2, 3, 4, 5]

# Multiplier chaque élément par 2
resultat = list(map(lambda x: x * 2, nombres))
print(resultat)  # [2, 4, 6, 8, 10]
```

---

### 2.2 `filter()` - Filtrer les éléments selon une condition
```python
nombres = [10, 15, 21, 30, 35]

# Conserver seulement les multiples de 5
multiples_de_5 = list(filter(lambda x: x % 5 == 0, nombres))
print(multiples_de_5)  # [10, 15, 30, 35]
```

---

### 2.3 `sorted()` - Trier des éléments
```python
noms = ["Alice", "bob", "charlie"]

# Trier par ordre alphabétique (insensible à la casse)
print(sorted(noms, key=str.lower))  # ['Alice', 'bob', 'charlie']

# Trier un dictionnaire par valeur
etudiants = {"Alice": 15, "Bob": 12, "Charlie": 18}
print(sorted(etudiants.items(), key=lambda x: x[1]))  
# [('Bob', 12), ('Alice', 15), ('Charlie', 18)]
```

---

### 2.4 `reduce()` - Réduction d'une liste
```python
from functools import reduce

nombres = [1, 2, 3, 4, 5]

# Somme des éléments
somme = reduce(lambda x, y: x + y, nombres)
print(somme)  # 15
```

---

## 3. Manipulation de Fichiers
Python permet de **lire et écrire des fichiers** facilement.

### 3.1 Lecture de fichiers
```python
with open("data.txt", "r", encoding="utf-8") as fichier:
    contenu = fichier.read()
    print(contenu)
```

### 3.2 Écriture dans un fichier
```python
with open("sortie.txt", "w", encoding="utf-8") as fichier:
    fichier.write("Bonjour, ceci est un test.")
```

### 3.3 Lecture ligne par ligne
```python
with open("data.txt", "r", encoding="utf-8") as fichier:
    for ligne in fichier: # ou fichier.readlines()
        print(ligne.strip())  # Supprime les espaces et sauts de ligne
```

---

## Conclusion
Ce rappel sur les **collections Python, les fonctions `map`, `filter`, `sorted`, `reduce`, et la manipulation de fichiers** constitue une base essentielle pour **l’analyse de données**.