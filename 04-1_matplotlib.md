# Visualisation de données avec Matplotlib et Pandas

## Objectifs du cours
À la fin de ce cours, vous serez capable de :
- Comprendre les concepts de base de la visualisation de données.
- Utiliser **Matplotlib** pour créer des graphiques simples et avancés.
- Manipuler des données avec **Pandas** et les visualiser efficacement.
- Personnaliser vos graphiques pour une meilleure présentation des données.
- Construire des **dashboards** et des **graphiques interactifs**.

---

#### Installation et importation
- Installation des bibliothèques nécessaires
  ```python
  pip install matplotlib pandas
  ```
- Importation des bibliothèques
  ```python
  import pandas as pd
  import matplotlib.pyplot as plt
  ```

---

### 2. Introduction à Matplotlib
#### 2.1 Création d'un graphique simple
- Structure d’un graphique Matplotlib
- La méthode `plot()`
- Exemple :
  ```python
  x = [1, 2, 3, 4, 5]
  y = [10, 20, 25, 30, 40]

  plt.plot(x, y, marker='o', linestyle='-', color='b')
  plt.xlabel("X-axis")
  plt.ylabel("Y-axis")
  plt.title("Graphique simple avec Matplotlib")
  plt.show()
  ```

#### 2.2 Personnalisation des graphiques
- Ajouter des **légendes, étiquettes et titres**
- Modifier les **couleurs, styles et épaisseurs**
- Changer la **taille du graphique**
  ```python
  plt.figure(figsize=(8, 5))
  plt.plot(x, y, marker='s', linestyle='--', color='r', linewidth=2)
  plt.xlabel("X-axis", fontsize=12)
  plt.ylabel("Y-axis", fontsize=12)
  plt.title("Personnalisation des graphiques", fontsize=14)
  plt.legend(["Ligne 1"], loc="upper left")
  plt.grid(True)
  plt.show()
  ```

#### 2.3 Tracer plusieurs courbes sur un même graphique
  ```python
  x = range(1, 6)
  y1 = [1, 4, 9, 16, 25]
  y2 = [1, 8, 27, 64, 125]

  plt.plot(x, y1, 'r-o', label="Carré")
  plt.plot(x, y2, 'b--s', label="Cube")
  plt.xlabel("X-axis")
  plt.ylabel("Y-axis")
  plt.title("Graphique avec plusieurs courbes")
  plt.legend()
  plt.show()
  ```

---

### 3. Types de Graphiques avec Matplotlib
#### 3.1 Histogrammes
- Distribution des données
  ```python
  data = [10, 20, 20, 30, 30, 30, 40, 50, 50, 60]
  plt.hist(data, bins=5, color='blue', edgecolor='black')
  plt.xlabel("Valeurs")
  plt.ylabel("Fréquence")
  plt.title("Histogramme")
  plt.show()
  ```

#### 3.2 Diagrammes en barres
- Comparaison de catégories
  ```python
  categories = ["A", "B", "C", "D"]
  valeurs = [5, 7, 3, 8]

  plt.bar(categories, valeurs, color=['red', 'blue', 'green', 'orange'])
  plt.xlabel("Catégories")
  plt.ylabel("Valeurs")
  plt.title("Diagramme en barres")
  plt.show()
  ```

#### 3.3 Diagrammes circulaires (Pie Charts)
  ```python
  labels = ["A", "B", "C", "D"]
  sizes = [30, 20, 40, 10]

  plt.pie(sizes, labels=labels, autopct='%1.1f%%', colors=['gold', 'lightblue', 'red', 'green'])
  plt.title("Diagramme circulaire")
  plt.show()
  ```

#### 3.4 Nuages de points (Scatter Plot)
  ```python
  import numpy as np
  x = np.random.rand(50)
  y = np.random.rand(50)
  plt.scatter(x, y, color='purple')
  plt.xlabel("X-axis")
  plt.ylabel("Y-axis")
  plt.title("Nuage de points")
  plt.show()
  ```
---

### 4. Visualisation avec Pandas
#### 4.1 Charger et manipuler des données
- Charger un fichier CSV
  ```python
  df = pd.read_csv("data.csv")
  print(df.head())
  ```
- Statistiques rapides
  ```python
  print(df.describe())
  ```

#### 4.2 Tracer des graphiques avec Pandas
- **Histogramme**
  ```python
  df['colonne'].hist(bins=10, color='blue')
  plt.title("Distribution des valeurs")
  plt.show()
  ```
- **Diagramme en barres**
  ```python
  df.groupby("catégorie")["valeur"].sum().plot(kind='bar', color='green')
  plt.title("Valeurs par catégorie")
  plt.show()
  ```
- **Courbes**
  ```python
  df.plot(x="date", y="prix", kind="line", marker="o")
  plt.title("Évolution des prix")
  plt.show()
  ```