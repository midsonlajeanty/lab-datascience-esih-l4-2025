# Introduction à NumPy

## Qu'est-ce que NumPy ?
NumPy (Numerical Python) est une bibliothèque fondamentale pour le calcul numérique en Python. Elle permet la manipulation efficace des tableaux multidimensionnels et fournit des fonctions mathématiques optimisées.

### Objectifs du cours
À la fin de ce cours, vous serez capable de :
- Comprendre l'utilité de NumPy
- Créer et manipuler des tableaux NumPy
- Effectuer des opérations mathématiques avancées sur les tableaux
- Optimiser le traitement des données en utilisant NumPy

## 1. Installation de NumPy
Si NumPy n'est pas encore installé, utilisez la commande suivante :
```python
pip install numpy
```

## 2. Création et manipulation des tableaux NumPy
### 2.1 Création d'un tableau NumPy
```python
import numpy as np

# Création d'un tableau 1D
arr1 = np.array([1, 2, 3, 4, 5])
print(arr1)

# Création d'un tableau 2D
arr2 = np.array([[1, 2, 3], [4, 5, 6]])
print(arr2)
```

### 2.2 Propriétés des tableaux
```python
print(arr2.shape)  # Dimensions du tableau
print(arr2.ndim)   # Nombre de dimensions
print(arr2.size)   # Nombre total d'éléments
print(arr2.dtype)  # Type de données
```

### 2.3 Création de tableaux spéciaux
```python
zeros = np.zeros((3, 3))  # Tableau de zéros
ones = np.ones((2, 2))    # Tableau de uns
rand = np.random.rand(3, 3)  # Tableau de nombres aléatoires
print(zeros, ones, rand)
```

## 3. Opérations sur les tableaux NumPy
### 3.1 Opérations arithmétiques
```python
arr = np.array([1, 2, 3, 4])
print(arr + 2)  # Addition scalaire
print(arr * 3)  # Multiplication scalaire
print(arr ** 2) # Puissance
```

### 3.2 Opérations entre tableaux
```python
arr1 = np.array([1, 2, 3])
arr2 = np.array([4, 5, 6])
print(arr1 + arr2)  # Addition élément par élément
print(arr1 * arr2)  # Multiplication élément par élément
```

### 3.3 Fonctions mathématiques
```python
arr = np.array([1, 4, 9, 16])
print(np.sqrt(arr))  # Racine carrée
print(np.log(arr))   # Logarithme naturel
print(np.sin(arr))   # Sinus
```

## 4. Indexation et Slicing
```python
arr = np.array([10, 20, 30, 40, 50])
print(arr[0])    # Premier élément
print(arr[-1])   # Dernier élément
print(arr[1:4])  # Sous-tableau du deuxième au quatrième élément
```

## 5. Manipulation des tableaux
### 5.1 Reshape (changement de forme)
```python
arr = np.array([1, 2, 3, 4, 5, 6])
reshaped = arr.reshape((2, 3))
print(reshaped)
```

### 5.2 Concatenation
```python
arr1 = np.array([[1, 2], [3, 4]])
arr2 = np.array([[5, 6]])
concatenated = np.vstack((arr1, arr2))  # Concaténation verticale
print(concatenated)
```

## 6. Applications
NumPy est utilisé dans de nombreux domaines :
- Traitement de données et calcul scientifique
- Analyse statistique et machine learning
- Graphiques et simulations numériques

## Conclusion
NumPy est un outil puissant pour la manipulation efficace des données numériques. Sa maîtrise est essentielle pour toute analyse de données avancée en Python.

