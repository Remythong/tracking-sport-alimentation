# tracking-sport-alimentation
Projet de suivi et d’analyse de l’activité sportive et de l’alimentation (Google Sheets, dashboards)

### 🎯 Problématique analytique

Comment structurer, suivre et analyser dans le temps des données liées :

- à l’exercice physique,
- à l’apport en protéines,
- à la consommation de compléments,
- et à des habitudes personnalisées,

afin de mesurer la **régularité**, la **répartition**, le **volume**, et l’**atteinte d’objectifs définis**.

---

### 📊 Données utilisées

### Dimensions

- Date
- Groupe musculaire
- Type de complément alimentaire
- Type d’habitude

### Mesures

- Charge d’exercice
- Apport en protéines (alimentaire et complémentaire)
- Consommation de compléments
- Indicateurs de suivi d’habitudes
- Niveaux de stock de compléments

Les données sont saisies à une **granularité journalière**.

---

### 🗂️ Structure des données (Google Sheets)

Le projet repose sur plusieurs tables fonctionnelles :

- **Saisie**
    
    Table principale de saisie journalière, sous forme agrégée, permettant un suivi rapide des activités, apports et habitudes.
    
- **Saisie_Charge**
    
    Table dédiée au suivi des charges d’exercices, également agrégée par date.
    
- **Stock_Compléments**
    
    Tables de saisie indépendantes (réassort, pertes, taux protéiques), alimentant des calculs d’agrégation pour le suivi des niveaux de stock.
    
- **SETUP**
    
    Table de paramétrage des objectifs (sport, nutrition, habitudes), utilisée comme référence dans les dashboards.
    

👉 La structure actuelle est **optimisée pour la saisie utilisateur et la lisibilité**, dans un environnement Google Sheets.

---

### 📈 Indicateurs clés & dashboards

Le projet comprend plusieurs dashboards thématiques :

**Dashboard – Vue globale**

- Pourcentage d’objectifs atteints
- Indicateurs temporels de suivi
- Cohérence et continuité des données sur la période

**Dashboard – Activité sportive**

- Régularité des séances
- Répartition et équilibre des groupes musculaires
- Volume total et par groupe musculaire
- Proportion des exercices sur la période sélectionnée

**Dashboard – Alimentation & compléments**

- Apport total en protéines
- Répartition protéines alimentaires vs compléments
- Suivi de consommation par rapport aux objectifs
- Évolution temporelle de la consommation (interactif)

**Dashboard – Habitudes**

- Évolution annuelle et mensuelle de plusieurs habitudes
- Moyennes mensuelles et tendances

---

### 💡 Valeur ajoutée analytique

- Vision globale et temporelle avec filtres interactifs
- Mise en perspective des résultats par rapport à des objectifs définis
- Identification de déséquilibres (régularité, volume, répartition)
- Recommandations textuelles suggérant des axes d’amélioration
- Structure des dashboards en entonnoir : du global vers le détail

---

### ⚙️ Outils utilisés

- Google Sheets (saisie, transformations, dashboards)
- Power BI (à venir)

---

### 🔄 Normalisation & limites actuelles

La structure actuelle des données est volontairement **large (format “wide”)** et agrégée par date afin de faciliter la saisie manuelle.

Cette approche présente des limites pour :

- l’exploitation SQL,
- la scalabilité,
- et la modélisation analytique avancée.

👉 Une version ultérieure du projet prévoit :

- une **normalisation des données (format long)**,
- une séparation claire entre tables de faits et dimensions,
- une exploitation via Power BI et/ou une base de données relationnelle.

---

### 🧭 État du projet & roadmap

- ✅ Version actuelle : Google Sheets – Suivi & dashboards fonctionnels
- 🔨​ Actions intermédiaires : Rectification des disfonctionnements rencontrés et améliorations continues
- 🔜 Prochaines étapes :
    - Modélisation normalisée des données
    - Implémentation sous Power BI
    - Automatisation partielle de la collecte
    - Extension à un suivi financier (projet connexe)

---

## 👤 Auteur

Projet personnel réalisé par **Rémy Thong**, dans une démarche de montée en compétences en data analytics et dashboarding.
