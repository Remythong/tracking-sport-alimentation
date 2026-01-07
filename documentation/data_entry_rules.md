## Règles de saisie des données

### Projet Tracking Sport & Alimentation

---

### 🎯 Objectif

Garantir une **cohérence minimale des données** afin de permettre des analyses temporelles fiables et reproductibles, malgré une saisie manuelle dans Google Sheets.

---

### 📅 Règles générales

- Une seule ligne par date (granularité journalière)
- Les dates doivent être continues autant que possible (remplir manuellement en glissant)
- Les cellules non renseignées sont interprétées comme :
    - `0` pour les mesures quantitatives
    - `0 / 1` ou `FALSE / TRUE` pour les habitudes (selon implémentation)
- Aucune suppression de ligne historique (correction via modification de valeur)

---

### 🏋️ Activité sportive

- Les charges d’exercices sont saisies :
    - par groupe musculaire
    - sous forme numérique
- Une valeur nulle signifie :
    - absence d’entraînement pour le groupe concerné
- Les unités de charge sont cohérentes dans le temps (kg ou équivalent)

---

### 🥗 Alimentation & protéines

- Les apports en protéines sont distingués entre :
    - protéines alimentaires
    - protéines issues de compléments
- Les valeurs sont exprimées en grammes
- Les données correspondent à des estimations cohérentes, non à des mesures exactes

---

### 💊 Compléments alimentaires

- Le Restock correspondent aux réassorts
- Le relevé de perte correspond aux pertes dues à une mauvaise saisie/mauvaise précision physique/perte physique
- Les taux protéiques sont définis dans une table dédiée et utilisés dans les calculs
- Les niveaux de stock sont calculés automatiquement à partir des mouvements

---

### 🔁 Habitudes

- Les habitudes sont saisies :
    - sous forme numérique
- La définition d’une habitude reste constante sur la période analysée
- Toute modification d’habitude implique une rupture d’analyse à prendre en compte

---

### ⚠️ Incohérences connues et limites

- Saisie manuelle sujette à l’erreur humaine
- Absence de contrôle automatique de validité sur certaines saisies
- Dépendance à la régularité de l’utilisateur

---

### 🔄 Améliorations envisagées

- Mise en place de contrôles de validation
- Automatisation partielle de la saisie
- Historisation des changements de règles

---

## 📌 Note

Ce document vise à expliciter les **hypothèses et conventions** utilisées dans la version actuelle du projet.

Il permet d’interpréter correctement les analyses et dashboards produits.
