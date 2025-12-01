#  TP Final — GitHub, Collaboration & Revue de Code  
## Mini-API Catalogue (Node.js / Express) + Mini-TP Python

---

#  Objectifs pédagogiques

Ce TP vous permet de pratiquer de manière professionnelle :

- la collaboration via GitHub (branches, PR, review)  
- l’amélioration d’un projet Node.js existant  
- la détection d’erreurs dans un code volontairement imparfait  
- la création et gestion de Pull Requests  
- la revue de code constructive  
- l’écriture de tests Python (transition vers l’A/B Testing)

---

#  1. Récupération du projet


Cloner le projet :

```bash
git clone https://github.com/<organisation>/mini-api-catalogue.git
cd mini-api-catalogue
```

Installer les dépendances :

```bash
npm install
npm run dev
```

Vérifier que l’API fonctionne.

---

#  2. Travail en binôme

- Un **Auteur** : réalise la modification + crée la PR  
- Un **Reviewer** : analyse la PR + donne un feedback  
- Vous échangerez les rôles à la moitié du TP

Chaque binôme travaille dans le **même dépôt GitHub**.

---

#  3. Création d’une branche de fonctionnalité

À partir de `main` :

```bash
git checkout -b feature/<amelioration>
```

Exemples de noms :  
- `feature/correction-status-code`  
- `feature/validation-products`  
- `feature/clean-duplicate-code`

---

#  4. Analyse du code (obligatoire)

Dans le dépôt se trouvent volontairement :

- codes HTTP incorrects  
- duplications de logique  
- manque de validations  
- messages d’erreurs incohérents  
- structure imparfaite des routes  
- absence de middleware d’erreurs  

**Votre but : choisir UNE amélioration simple et ciblée.**

---

#  5. Amélioration à effectuer (Auteur)

Réaliser UNE amélioration, par exemple :

### ✔ Ajout d’une validation
Ex : vérifier qu’un produit a bien un `name`.

### ✔ Correction d’un code HTTP
Ex : changer un `500` en `404`, un `200` en `201`, etc.

### ✔ Refactorisation d’une duplication
Ex : extraire une fonction commune.

### ✔ Correction d’une mauvaise logique
Ex : erreur dans `/categories/:id`.

>  **Eviter les gros changements : privilégier une PR simple et propre.**

---

#  6. Commit + Push

```bash
git add .
git commit -m "Correction du code HTTP pour GET /products/:id"
git push origin feature/<amelioration>
```

---

#  7. Création de la Pull Request

Sur GitHub :

1. Aller dans **Pull Requests**  
2. Cliquer sur **New Pull Request**  
3. Base : `main`  
   Compare : `feature/<amelioration>`  
4. Remplir :
   - **Titre clair**
   - **Description complète**
   - Pourquoi cette correction ?
   - Comment la tester ?
5. Assigner votre reviewer

---

#  8. Revue de code (Reviewer)

Le reviewer doit vérifier :

- la logique  
- la cohérence  
- le style  
- l’absence de bug  
- la bonne pratique Git  

Et ajouter :

- commentaires  
- suggestions  
- demandes de correction si nécessaire

Faire preuve de **bienveillance + exigence**.

---

#  9. Corrections (Auteur)

L’auteur applique les retours :

```bash
git add .
git commit -m "Corrections suite aux commentaires"
git push
```

La PR se met à jour automatiquement.

---

#  10. Validation & Merge

Quand la PR est approuvée :

- cliquer **Merge Pull Request**  
- supprimer la branche (optionnel)

---

#  11. Inversion des rôles

Le reviewer devient Auteur.  
L’Auteur devient Reviewer.

Refaire les étapes **3 à 10** avec une autre amélioration.

---

#  12. Mini-TP Python — Écriture de tests

Créer un fichier `operations.py` :

```python
def addition(a, b):
    return a + b

def maximum(a, b):
    return a if a > b else b

def format_nom(prenom, nom):
    return f"{prenom.capitalize()} {nom.upper()}"
```

Créer un fichier `test.py` :

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

Lancer les tests :

```bash
python test.py
```

Créer une PR contenant les tests Python :

```bash
git checkout -b feature/tests-python
git add .
git commit -m "Ajout des tests Python"
git push origin feature/tests-python
```

---




