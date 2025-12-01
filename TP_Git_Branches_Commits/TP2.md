#  TP1 – Manipulation des branches, commits, push et fusion avec Git

Ce TP vous permet de pratiquer les bases essentielles de Git :
**commits, branches, push, merge et organisation du code**.

---

##  1. Travail sur la branche `main`

### **1.1 Créer le fichier `code.py`**
```python
from datetime import datetime

print("Hello ! Il est {}.".format(datetime.now().strftime("%H:%M:%S")))
```

### **1.2 Ajouter et committer**
```bash
git add code.py
git commit -m "Ajout du fichier code.py"
```

### **1.3 Afficher l’historique**
```bash
git log
```

### **1.4 Envoyer sur GitHub**
```bash
git push origin main
```

---

##  2. Création d’une nouvelle branche : `refonte`

### **2.1 Créer et basculer sur la branche**
```bash
git checkout -b refonte
```

---

##  3. Ajout d’un module dans la branche `refonte`

### **3.1 Créer un fichier `module.py`**
```python
from datetime import datetime

def obtenir_temps():
    return "Hello ! Il est {}.".format(datetime.now().strftime("%H:%M:%S"))
```

### **3.2 Modifier le fichier `code.py`**
```python
from module import obtenir_temps

print(obtenir_temps())
```

### **3.3 Committer les modifications**
```bash
git add module.py code.py
git commit -m "Ajout du module et mise à jour du code"
```

### **3.4 Envoyer la branche sur GitHub**
```bash
git push origin refonte
```

---

## 🔀 4. Fusion de la branche `refonte` dans `main`

### **4.1 Retourner sur `main`**
```bash
git checkout main
```

### **4.2 Fusionner la branche**
```bash
git merge refonte
```

### **4.3 Envoyer la branche principale mise à jour**
```bash
git push origin main
```

---

##  5. (Optionnel) Suppression de la branche `refonte`

### **5.1 Supprimer localement**
```bash
git branch -d refonte
```

### **5.2 Supprimer sur GitHub (si elle existe)**
```bash
git push origin --delete refonte
```

---


