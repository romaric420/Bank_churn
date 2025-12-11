# 🏦 Bank Churn Prediction

<div align="center">

![Python](https://img.shields.io/badge/Python-3.12-blue?style=for-the-badge&logo=python)
![XGBoost](https://img.shields.io/badge/XGBoost-2.0-green?style=for-the-badge&logo=xgboost)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.3-orange?style=for-the-badge&logo=scikit-learn)
![License](https://img.shields.io/badge/License-MIT-red?style=for-the-badge)

**Prédire le départ des clients bancaires avec Machine Learning 🚀**

[🎯 Démo](#-démo) • [📊 Dataset](#-dataset) • [🔧 Installation](#-installation) • [🚀 Utilisation](#-utilisation) • [📈 Résultats](#-résultats)

</div>

---

## 📖 À propos du projet

Ce projet a été développé dans le cadre d'une compétition Kaggle. 

Grâce à une analyse exploratoire approfondie (EDA), des tests statistiques et des modèles prédictifs, nous identifions les profils à risque .

NB: il ya des ameliorations a faire donc il yaura des mise a jour 
### 🎯 Objectif

Prédire la probabilité qu'un client quitte la banque en analysant :
- 👤 Informations démographiques (âge, genre, pays)
- 💰 Données financières (solde, salaire, crédit score)
- 🏦 Comportement bancaire (produits, activité, ancienneté)

---

## ✨ Fonctionnalités

- 📊 **Analyse exploratoire complète** des données
- 🧪 **Tests statistiques** (t-test, chi²) pour valider les hypothèses
- 🤖 **Modèle XGBoost optimisé** avec GridSearchCV
- ⚡ **Support GPU** pour accélérer l'entraînement
- 📈 **Pipeline sklearn** pour automatiser le preprocessing
- 🎯 **ROC-AUC optimisé** pour mesurer la performance

---

## 📊 Dataset

Le dataset contient **10 000 clients** avec les variables suivantes :

| Variable | Type | Description |
|----------|------|-------------|
| `CreditScore` | Numérique | Score de crédit (350-850) |
| `Geography` | Catégorielle | Pays (France, Allemagne, Espagne) |
| `Gender` | Catégorielle | Genre (Male, Female) |
| `Age` | Numérique | Âge du client |
| `Tenure` | Numérique | Années d'ancienneté (0-10) |
| `Balance` | Numérique | Solde du compte |
| `NumOfProducts` | Numérique | Nombre de produits (1-4) |
| `HasCrCard` | Binaire | Possession carte de crédit |
| `IsActiveMember` | Binaire | Membre actif |
| `EstimatedSalary` | Numérique | Salaire estimé |
| **`Exited`** | **Binaire** | **Cible : Client parti (1) ou non (0)** |

---

## 🔧 Installation

### Prérequis

- Python 3.12+
- Poetry (gestionnaire de dépendances)
- pyenv

### Installation rapide

```bash
# Cloner le repository
git clone https://github.com/ton-username/Bank_Churn.git
```

### Dépendances principales

```toml
pandas = "^2.0.0"
numpy = "^1.24.0"
scikit-learn = "^1.3.0"
xgboost = "^2.0.0"
matplotlib = "^3.7.0"
seaborn = "^0.12.0"
scipy = "^1.11.0"
```

---

## 🚀 Utilisation

### 1️⃣ Lancer l'analyse complète

```bash
poetry run python main.py
```

### 2️⃣ Entraîner le modèle

```python
from sklearn.model_selection import GridSearchCV
from xgboost import XGBClassifier

# Le pipeline complet est déjà configuré
grid_search.fit(X_train, y_train)

# Meilleurs paramètres
print(grid_search.best_params_)
```

### 3️⃣ Faire des prédictions

```python
# Charger les données de test
test_data = pd.read_csv("test_data.csv")

# Prédire
predictions = best_model.predict(test_data)

# Sauvegarder les résultats
results.to_csv("predictions.csv")
```

---

## 📈 Résultats

### 🏆 Performance du modèle

| Métrique | Score |
|----------|-------|
| F1-Score | 0. |

### 📊 Insights clés

#### ✅ Facteurs augmentant le churn :

1. 👴 **Âge élevé** - Les clients âgés partent plus
2. 💸 **Faible balance** - Moins d'argent = plus de départs
3. 📉 **Inactivité** - Les membres inactifs ont un churn massif
4. 🔢 **Peu de produits** - 1 seul produit = moins de fidélité
5. 🆕 **Nouveaux clients** - Les récents partent plus vite

#### 🌍 Différences géographiques :

- **Allemagne** : Taux de churn le plus élevé
- **France** : Taux de churn intermédiaire
- **Espagne** : Taux de churn le plus faible

---

## 🛠️ Architecture du projet

```
Bank_Churn/
├── 📊 train_data.csv          # Dataset d'entraînement
├── 📊 test_data.csv           # Dataset de test
├── 🐍 main.py                 # Script principal
├── 📓 analysis.ipynb          # Notebook d'analyse
├── 💾 best_model.pkl          # Modèle sauvegardé
├── 📄 predictions.csv         # Résultats des prédictions
├── 📦 pyproject.toml          # Dépendances Poetry
└── 📖 README.md               # Ce fichier
```

---

## 🔬 Méthodologie

### 1. Analyse exploratoire (EDA)
- Visualisations des distributions
- Analyse univariée et multivariée
- Détection des outliers
  

### 2. Tests statistiques
- **t-test** : Variables continues vs catégorielles
- **Chi²** : Variables catégorielles vs catégorielles
- Validation des hypothèses avec α = 0.02

### 3. Preprocessing
```python
Pipeline:
├─ OneHotEncoder (Geography, Gender)
├─ PolynomialFeatures (degree=2)
├─ SelectKBest (k=30)
└─ StandardScaler
```

### 4. Modélisation
- **Modèle** : XGBoost Classifier
- **Optimisation** : GridSearchCV (5-fold CV)
- **Accélération** : GPU avec CUDA

---

## 🎯 Améliorations futures

- [ ] 🧠 Tester d'autres modèles (LightGBM, CatBoost)
- [ ] 🔄 Créer un ensemble de modèles, ameliorer le score f1
- [ ] 🎨 Développer un dashboard interactif (Streamlit/Dash)
- [ ] 🚀 Déployer l'API (FastAPI + Docker)
- [ ] 📊 Feature engineering avancé
- [ ] ⚖️ Gérer le déséquilibre des classes (SMOTE)

---

## 🤝 Contribution

Les contributions sont les bienvenues ! 

1. Fork le projet
2. Créer une branche (`git checkout -b feature/AmazingFeature`)
3. Commit les changements (`git commit -m 'Add AmazingFeature'`)
4. Push vers la branche (`git push origin feature/AmazingFeature`)
5. Ouvrir une Pull Request

---

## 📝 License

Ce projet est sous licence MIT. Voir le fichier `LICENSE` pour plus de détails.

---

## 👤 Auteur

**Romaric420**


- 📧 Email: hippolytetchoffo3@gmail.com
- 

---

## 🙏 Remerciements

- 📚 ML-Pro pour les Cours


---

<div align="center">

**⭐ N'oublie pas de star le projet si tu l'as trouvé utile ! ⭐**

Made with ❤️ and ☕ by Romaric420

</div>
