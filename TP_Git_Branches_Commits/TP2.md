# 🧪 TP2 – Création et résolution d’un conflit de merge avec Git

Ce TP vous permet de provoquer volontairement un **conflit Git**, de l’observer et de le résoudre dans le même dépôt utilisé pour le TP1.

---

##  1. Vérifier l’état du dépôt

Assurez-vous que votre dépôt est propre :

```bash
git status
```

S’il reste des modifications non commit :
```bash
git add .
git commit -m "Sauvegarde avant conflit"
```

Ou pour mettre de côté :
```bash
git stash
```

---

##  2. Créer une première branche `conflit-a`

```bash
git checkout -b conflit-a
```

Modifier le fichier **code.py** (version A du conflit) :

```python
print("Version A du code")
```

Commit :

```bash
git add code.py
git commit -m "Modification version A"
```

---

##  3. Retour sur `main`

```bash
git checkout main
```

---

##  4. Créer une deuxième branche `conflit-b`

```bash
git checkout -b conflit-b
```

Modifier **code.py** différemment (version B du conflit) :

```python
print("Version B du code")
```

Commit :

```bash
git add code.py
git commit -m "Modification version B"
```

---

##  5. Fusionner la première branche dans `main`

```bash
git checkout main
git merge conflit-a
```

La fusion fonctionne sans conflit.

---

##  6. Fusionner la branche `conflit-b` (conflit garanti)

```bash
git merge conflit-b
```

Message attendu :

```
Auto-merging code.py
CONFLICT (content): Merge conflict in code.py
Automatic merge failed; fix conflicts and then commit the result.
```

---

##  7. Observer le conflit

Ouvrir **code.py** :

```txt
<<<<<<< HEAD
print("Version A du code")
=======
print("Version B du code")
>>>>>>> conflit-b
```

Ces marqueurs indiquent le conflit.

---

##  8. Résoudre le conflit

Choisir une version finale (par exemple) :

```python
print("Version finale du code après résolution du conflit")
```

Valider la résolution :

```bash
git add code.py
git commit -m "Résolution du conflit entre conflit-a et conflit-b"
git push origin main
```


