# Cours sur le Web Scraping avec Python

## Introduction
Le **Web Scraping** est une technique permettant d'extraire des données de sites web de manière automatique. Cette pratique est utilisée pour collecter des informations accessibles publiquement, comme les prix de produits, les actualités ou les avis clients. Python est l'un des langages les plus populaires pour le web scraping grâce à ses bibliothèques puissantes telles que **BeautifulSoup**, **Requests**, et **Selenium**.

---

## Objectifs du cours
- Comprendre les bases du Web Scraping.
- Apprendre à extraire et analyser des données à partir de pages web.
- Utiliser **BeautifulSoup** et **Requests** pour extraire des informations.
- Automatiser le scraping avec **Selenium** pour les pages dynamiques.
- Respecter les bonnes pratiques et les règles éthiques du scraping.

---

## 1. Bases du Web Scraping

### 1.1 Comment fonctionne le Web Scraping ?
Le processus de scraping suit plusieurs étapes :
1. **Envoyer une requête HTTP** au site web cible.
2. **Récupérer le contenu HTML** de la page.
3. **Analyser le HTML** pour extraire les données pertinentes.
4. **Stocker ou traiter les données** selon les besoins.

### 1.2 Règles éthiques et légales
- **Respecter le fichier robots.txt** qui indique les pages autorisées à l'exploration.
- **Ne pas surcharger les serveurs** avec des requêtes trop fréquentes.
- **Vérifier les conditions d'utilisation** du site web cible.

---

## 2. Outils et Bibliothèques

### 2.1 Installation des bibliothèques
```bash
pip install requests beautifulsoup4 selenium
```

### 2.2 Bibliothèque Requests
La bibliothèque **Requests** permet d'envoyer des requêtes HTTP et de récupérer le contenu des pages web.

#### Exemple : Récupération d'une page web
```python
import requests

url = "https://example.com"
response = requests.get(url)
print(response.text)  # Affiche le contenu HTML de la page
```

### 2.3 Bibliothèque BeautifulSoup
**BeautifulSoup** permet d'analyser et de naviguer dans le HTML.

#### Exemple : Extraction de données HTML
```python
from bs4 import BeautifulSoup

html = """
<html>
    <body>
        <h1>Bienvenue</h1>
        <p class='info'>Ceci est un test de scraping.</p>
    </body>
</html>
"""

soup = BeautifulSoup(html, "html.parser")
titre = soup.find("h1").text
paragraphe = soup.find("p", class_="info").text
print(titre)  # Affiche "Bienvenue"
print(paragraphe)  # Affiche "Ceci est un test de scraping."
```

---

## 3. Scraping d'un site web

### 3.1 Extraction d'informations

#### Exemple : Récupération des titres d'articles d'un blog
```python
url = "https://example-blog.com"
response = requests.get(url)
soup = BeautifulSoup(response.text, "html.parser")

for article in soup.find_all("h2", class_="title"):
    print(article.text)
```

### 3.2 Gestion des en-têtes et des délais

```python
headers = {"User-Agent": "Mozilla/5.0"}
response = requests.get(url, headers=headers)
```

---

## 4. Scraping de pages dynamiques avec Selenium

Certaines pages sont générées dynamiquement avec JavaScript. **Selenium** permet d'interagir avec ces pages.

### 4.1 Installation de Selenium
```bash
pip install selenium
```

### 4.2 Exemple avec ChromeDriver
```python
from selenium import webdriver
from selenium.webdriver.common.by import By

# Configuration du navigateur
options = webdriver.ChromeOptions()
options.add_argument("--headless")
driver = webdriver.Chrome(options=options)

driver.get("https://example.com")
titre = driver.find_element(By.TAG_NAME, "h1").text
print(titre)

driver.quit()
```

## Conclusion
Le Web Scraping est une technique puissante pour extraire des données sur le web. **Requests** et **BeautifulSoup** permettent de scraper des pages statiques, tandis que **Selenium** est utile pour les sites dynamiques. Il est essentiel de respecter les bonnes pratiques éthiques et légales lors de la collecte d'informations.

Bonne exploration du Web Scraping !

