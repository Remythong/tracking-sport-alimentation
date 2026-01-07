## Modèle de données – Projet Tracking Sport & Alimentation

### 🎯 Objectif du modèle

Structurer des données issues d’un suivi quotidien de l’activité sportive, de l’alimentation et d’habitudes personnalisées, afin de permettre une analyse temporelle, la construction de dashboards et la comparaison à des objectifs définis.

Le modèle actuel est conçu dans un environnement **Google Sheets**, avec une priorité donnée à la **simplicité de saisie utilisateur**.

---

### 📅 Granularité

- **Granularité principale : journalière**
- Une ligne correspond à **une date**
- Les données sont agrégées par jour

---

### 🗂️ Tables du modèle

### 1️⃣ Table `Saisie`

Table principale regroupant les informations de suivi quotidien.

**Rôle :**

- Centraliser les données sport, nutrition et habitudes
- Servir de base aux calculs et dashboards globaux

**Champs principaux (exemples) :**

- `date`
- `groupe_musculaire_pectoraux`
- `groupe_musculaire_dos`
- `groupe_musculaire_jambes`
- `proteines_alimentaires_g`
- `proteines_complements_g`
- `habitude_1`
- `habitude_2`
- `habitude_3`
- `habitude_4`

👉 Structure volontairement **large (format wide)** afin de faciliter la saisie manuelle.

---

### 2️⃣ Table `Saisie_Charge`

Table dédiée au suivi des charges d’exercices.

**Rôle :**

- Suivre la progression de charge des exercices
- Alimenter les indicateurs de charge et de progression

**Champs principaux (exemples) :**

- `Date`
- `DVP_hal`
- `Tir_poulie`
- `DM_hal`
- `Bar_front`
- `Curl_bar`

Granularité identique à la table `Saisie`.

---

### 3️⃣ Table `Stock_Complements`

Tables de saisie liées au suivi des compléments alimentaires.

**Rôle :**

- Suivre les niveaux de stock dans le temps
- Calculer la consommation et anticiper les besoins de réassort

**Sous-ensembles fonctionnels :**

- Réassort des compléments
- Déclaration de pertes
- Paramétrage des taux protéiques

**Champs principaux (exemples) :**

- `date`
- `type_complement`
- `quantite_entree`
- `quantite_sortie`
- `taux_proteines`

---

### 4️⃣ Table `SETUP`

Table de paramétrage utilisée comme référence par les dashboards.

**Rôle :**

- Centraliser les objectifs personnalisés
- Définir les seuils et cibles analytiques

**Champs principaux (exemples) :**

- `objectif_proteines_journalier`
- `objectif_seances_semaine`

---

### 🔗 Relations conceptuelles

Dans la version actuelle :

- Les tables sont reliées **implicitement par la date**
- Il n’existe pas de clés techniques ou de relations explicites (type clé primaire / clé étrangère)

👉 Cette approche est adaptée à Google Sheets, mais présente des limites pour une exploitation relationnelle avancée.

---

### ⚠️ Limites actuelles du modèle

- Format de données **large (wide)** peu adapté au SQL
- Agrégation journalière limitant certaines analyses fines
- Absence de tables de dimensions explicites (groupes musculaires, types de compléments, habitudes)
- Modèle optimisé pour la saisie, pas pour la scalabilité

---

### 🔄 Évolutions envisagées

Une version ultérieure du modèle prévoit :

- Une **normalisation des données (format long)**
- La séparation entre tables de faits et tables de dimensions
- Une exploitation via Power BI et/ou une base relationnelle
- Une automatisation partielle de l’alimentation des données

---

## 📌 Note

Ce document décrit le **modèle actuel utilisé dans la version Google Sheets du projet**.

Il sert de base de réflexion pour les évolutions futures et n’a pas vocation à être figé.
