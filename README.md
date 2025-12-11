# Bank_churn
<div align="center"><img src="https://i.imgur.com/T0skH5M.gif" alt="Bank Churn Prediction Banner" width="100%" style="border-radius: 10px;">🏦 Bank Churn PredictionCompétition Kaggle : Analyse et prédiction de l'attrition client</div>📖 Vue d'ensembleCe projet a été développé dans le cadre d'une compétition Kaggle. L'objectif est de déployer une solution de Machine Learning capable de prédire l'attrition client (churn) dans le secteur bancaire.Grâce à une analyse exploratoire approfondie (EDA), des tests statistiques rigoureux et des modèles prédictifs, nous identifions les profils à risque pour permettre aux banques de mettre en place des actions de rétention ciblées.🎯 Objectifs PrincipauxPrédire la variable cible Exited en exploitant trois axes de données :👤 Démographie : Âge, genre, localisation géographique.💰 Finances : Solde du compte, salaire estimé, score de crédit.🏦 Comportement : Nombre de produits, niveau d'activité, ancienneté.✨ Fonctionnalités Clés📊 EDA Approfondi : Visualisation des distributions et analyse des corrélations multivariées.🧪 Validation Statistique : Tests d'hypothèses rigoureux (t-test, chi²) avec un seuil $\alpha = 0.02$.⚙️ Pipeline Automatisé : Preprocessing via Scikit-learn (OneHotEncoder, PolynomialFeatures).⚡ Entraînement GPU : Modèle XGBoost accéléré et optimisé via GridSearchCV.🎯 Focus Métrique : Évaluation centrée sur le F1-Score pour gérer le déséquilibre des classes.📊 Le DatasetLe jeu de données comporte 10 000 entrées clients.Variable CléTypeDescription ConciseCreditScoreNumériqueScore de crédit (350-850)GeographyCatégoriellePays (France, Allemagne, Espagne)AgeNumériqueÂge du clientTenureNumériqueAnnées d'ancienneté (0-10)BalanceNumériqueSolde du compte bancaireNumOfProductsNumériqueNombre de produits détenus (1-4)IsActiveMemberBinaireIndicateur d'activité récenteExitedBinaireCible : Client parti (1) ou resté (0)🔧 Installation et ConfigurationLa gestion des dépendances est assurée par Poetry pour garantir la reproductibilité de l'environnement.Prérequis : Python 3.12+ et Poetry installé.Bash# 1. Cloner le dépôt
git clone https://github.com/votre-username/Bank_Churn.git
cd Bank_Churn

# 2. Installer les dépendances
poetry install

# 3. Activer l'environnement virtuel
poetry shell
🚀 UtilisationLancer l'analyse complèteBashpoetry run python main.py
Snippet d'entraînement (Aperçu)Pythonfrom sklearn.model_selection import GridSearchCV
from xgboost import XGBClassifier

# Le pipeline complet est pré-configuré dans le projet
grid_search.fit(X_train, y_train)

# Affichage des meilleurs hyperparamètres trouvés
print(f"Best Params: {grid_search.best_params_}")
📈 Résultats et Performances<div align="center">Performance ActuelleLe modèle actuel atteint le score suivant sur le jeu de test :🔥 Métrique Principale 🔥Score ObtenuF1-Score0.62329</div>🧠 Insights MétierL'analyse a permis de dégager des facteurs de risque critiques :✅ Facteur Âge : Forte corrélation entre l'augmentation de l'âge et le taux de départ.✅ Solde Critique : Les clients avec un faible solde sont plus volatils.✅ L'Inactive Member : L'inactivité est un précurseur majeur du churn.✅ Géographie : L'Allemagne présente le taux d'attrition le plus élevé du dataset.🛠️ Structure du ProjetBashBank_Churn/
├── 📊 data/                   # Données brutes (train/test)
├── 🐍 src/                    # Code source
│   ├── main.py                # Point d'entrée principal
│   └── preprocessing.py       # Pipelines de transformation
├── 📓 notebooks/              # Analyse exploratoire (EDA & Tests Stats)
├── 💾 models/                 # Modèles sérialisés (.pkl)
├── 📄 results/                # Prédictions et rapports
├── 📦 pyproject.toml          # Configuration Poetry
└── 📖 README.md               # Documentation
🔮 Améliorations Futures (Roadmap)Notre objectif principal est l'amélioration continue de la métrique clé.[ ] 🎯 Priorité Absolue : Augmenter le F1-Score (Objectif : dépasser significativement 0.62329).[ ] 🧠 Benchmark Modèles : Tester LightGBM et CatBoost, souvent performants sur ce type de données tabulaires.[ ] ⚖️ Gestion du Déséquilibre : Implémenter des techniques avancées (SMOTE, ADASYN ou Class Weights) pour booster le Recall.[ ] 🔄 Stacking : Créer un méta-modèle (Ensemble Learning) pour combiner les prédictions.[ ] 🎨 Déploiement : Création d'un dashboard interactif Streamlit pour visualiser les résultats.<div align="center">Auteur : Romaric420💼 Profil GitHub<img src="https://img.shields.io/badge/Made%20with-Love%20and%20Code-red?style=for-the-badge" alt="Made with love">⭐ Si ce projet vous a été utile, n'hésitez pas à lui donner une étoile ! ⭐</div>
