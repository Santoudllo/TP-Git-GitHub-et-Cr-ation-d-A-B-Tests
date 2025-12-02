
# TP3 — Création d’une API Node.js + Collaboration GitHub + Tests Python

##  Objectifs pédagogiques
- Construire une API Node.js avec une structure professionnelle.
- Collaborer via GitHub : branches, Pull Requests, revue de code.
- Améliorer et corriger du code existant.
- Écrire des tests simples en Python.
- Documenter correctement une API.

---

#  PARTIE 1 — Création d’une API Node.js

## 1. Structure du projet à créer

Reproduisez la structure suivante :

```
mini-api-catalogue/
│
├── data/
│   ├── categories.json
│   └── products.json
│
├── routes/
│   ├── categories.js
│   └── products.js
│
├── server.js
├── package.json
└── README.md
```

## 2. Description des dossiers

###  data/
Mini base de données en JSON :
- `categories.json`
- `products.json`

###  routes/
Contient les fichiers de définition des endpoints :
- `categories.js`
- `products.js`

###  server.js
Point d’entrée de l’API :
- configuration du serveur  
- chargement des routes  
- lancement sur un port  

### 📄 package.json
Créé via `npm init`, contient dépendances & scripts.

### 📄 README.md
Documentation : installation, lancement, liste des endpoints.

---

## 3. Étapes pour créer l’API

1. Créer le dossier :
```
mkdir mini-api-catalogue
cd mini-api-catalogue
```

2. Créer les dossiers :
```
mkdir data
mkdir routes
```

3. Créer les fichiers vides :
```
server.js
README.md
data/categories.json
data/products.json
routes/categories.js
routes/products.js
```

---

## 4. Travail demandé 

- Ajouter quelques données dans les fichiers JSON.
- Programmer les endpoints CRUD dans les routes.
- Configurer `server.js`.
- Documenter l’API dans `README.md`.

---

#  PARTIE 2 — Collaboration GitHub (Binôme)

## 1. Rôles
- **Auteur** : réalise une amélioration + crée une PR.
- **Reviewer** : analyse la PR + commente + demande corrections.
- Inversion des rôles à mi-parcours.

---

## 2. Créer une branche de fonctionnalité
```
git checkout -b feature/<amelioration>
```

Exemples :
- `feature/correction-status-code`
- `feature/validation-products`

---

## 3. Analyse du code
Identifier une amélioration parmi :
- codes HTTP incorrects  
- validations manquantes  
- duplications  
- incohérences dans les routes  
- absence de middleware d’erreur  

➡️ **Choisir UNE amélioration simple.**

---

## 4. Réalisation de l’amélioration
- Effectuer l'amélioration sans modifier l'ensemble du projet.
- Garder une PR propre et lisible.

---

## 5. Commit & Push
```
git add .
git commit -m "Description de l'amélioration"
git push origin feature/<amelioration>
```

---

## 6. Création de la Pull Request
Sur GitHub :
- Aller dans **Pull Requests**
- **New Pull Request**
- Base : `main`
- Compare : `feature/<amelioration>`

Inclure :
- Titre clair  
- Description complète  
- Justification  
- Instructions de test

Assigner le reviewer.

---

## 7. Revue de code (Reviewer)
Vérifier :
- logique  
- cohérence  
- style  
- absence de bugs  
- bonnes pratiques Git  

Ajouter :
- commentaires  
- suggestions  
- demandes de correction  

---

## 8. Corrections
L’auteur applique les retours :
```
git add .
git commit -m "Corrections suite à review"
git push
```

La PR se met à jour automatiquement.

---

## 9. Merge
Lorsque validé :
- **Merge Pull Request**
- supprimer la branche (optionnel)

---

## 10. Inversion des rôles
- Le reviewer devient auteur.
- Nouvelle fonctionnalité.
- Nouvelle PR / review.

---

#  PARTIE 3 — Mini-TP Python : Tests

## 1. Créer `operations.py`
Contenant 3 fonctions :
- addition
- maximum
- format_nom

## 2. Créer `test.py`
Écrire des tests unitaires simples.

## 3. Lancer les tests
```
python test.py
```

## 4. Créer une PR dédiée
```
git checkout -b feature/tests-python
git add .
git commit -m "Ajout des tests Python"
git push origin feature/tests-python
```

---

