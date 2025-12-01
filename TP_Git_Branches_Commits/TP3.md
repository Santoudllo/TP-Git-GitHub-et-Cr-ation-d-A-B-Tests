#  TP GitHub & Collaboration — Revue de Code + Mini-TP Python (Tests)

##  Objectifs du TP
- Collaborer via GitHub (branches, PR, reviews)
- Améliorer un projet Node.js existant
- Réaliser une revue de code structurée
- Produire et corriger une Pull Request
- Introduire la logique des tests (Python) avant l’A/B Testing

---

#  1. Contexte du projet : Mini-API Catalogue
API Node.js / Express composée de deux endpoints :
- `/products`
- `/categories`

Le code contient volontairement :
- duplications de logique
- absence de validation
- erreurs HTTP
- structure perfectible

---

#  2. Travail en binôme
- 1 auteur + 1 reviewer
- Dépôt GitHub partagé
- Vous échangez les rôles à mi-parcours

---

#  3. Préparation du projet

```bash
git clone https://github.com/.../mini-api-catalogue.git
cd mini-api-catalogue
npm install
npm run dev
```

---

#  4. Création d’une branche de fonctionnalité

```bash
git checkout -b feature/ajout-endpoint
```

---

#  5. Modification à effectuer (Auteur)

Réalisez une amélioration simple :
- Ajouter une validation
- Ajouter un test
- Corriger un code HTTP incohérent
- Factoriser une logique dupliquée
- Corriger un bug simple

---

#  6. Commit & Push

```bash
git add .
git commit -m "Ajout validation sur POST /products"
git push origin feature/ajout-endpoint
```

---

#  7. Création de la Pull Request

Sur GitHub :
- New Pull Request
- Base : `main`
- Compare : `feature/...`
- Ajouter un titre clair + description détaillée
- Assigner un reviewer

---

#  8. Travail du Reviewer

Le reviewer vérifie :
- Qualité du code
- Logique
- Risques de bug
- Style et conventions

Il ajoute :
- Commentaires
- Suggestions
- Demandes de modifications

---

#  9. Corrections et mise à jour

```bash
git add .
git commit -m "Corrections suite aux retours du reviewer"
git push
```

---

#  10. Validation & fusion
- Merge Pull Request
- Supprimer la branche (optionnel)

---

#  11. Inversion des rôles
Le reviewer devient auteur  
L’auteur devient reviewer  
Répétez les étapes 4 → 10

---

#  12. Mini-TP Python (Tests)

##  Objectifs :
- Écrire 3 petites fonctions Python
- Ajouter un fichier `test.py`
- Tester avec `assert`
- Push → PR → review

---

### 12.1 Créer un fichier `operations.py`

```python
def addition(a, b):
    return a + b

def maximum(a, b):
    return a if a > b else b

def format_nom(prenom, nom):
    return f"{prenom.capitalize()} {nom.upper()}"
```

---

### 12.2 Créer un fichier `test.py`

```python
from operations import addition, maximum, format_nom

def test_addition():
    assert addition(2, 3) == 5

def test_maximum():
    assert maximum(10, 4) == 10

def test_format_nom():
    assert format_nom("luc", "martin") == "Luc MARTIN"

print("Tous les tests sont passés !")
```

---

### 12.3 Exécuter les tests

```bash
python test.py
```

---

### 12.4 Envoyer via PR

```bash
git checkout -b feature/tests-python
git add .
git commit -m "Ajout tests Python"
git push origin feature/tests-python
```

Ouvrir une PR puis faire une review croisée.

---


