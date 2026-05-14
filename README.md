# Stress Testing — Monte Carlo + IA vs Analyse Déterministe

**Contexte** : Rapport de stage — OCP Jorf Lasfar, UP-AP  
**Période** : Données historiques 2018-2025 | Simulation 10 000 scénarios  
**Outil** : Python 3 / Google Colab

## Objectif
Comparer la richesse et la précision d'une simulation Monte Carlo couplée à l'Intelligence Artificielle (K-Means, Isolation Forest) avec l'analyse de sensibilité déterministe traditionnelle à 2 variables (grille Excel 5×5). Validation de l'hypothèse H3 sur la supériorité du dispositif augmenté en stress testing.

## Contenu du notebook
- Données historiques OCP (2018-2025) : 5 variables corrélées (Roche, DAP, Soufre, Ammoniaque, USD/MAD)
- **Partie 1 — Monte Carlo + IA** :
  - Simulation de 10 000 scénarios avec corrélations réelles (décomposition de Cholesky)
  - Régression OLS + validation LOOCV
  - Clustering K-Means (K=5) pour identification des régimes de risque
  - Détection des stress sévères par Isolation Forest
  - Bootstrap (200 itérations) pour robustesse des intervalles de confiance
- **Partie 2 — Méthode classique** :
  - Grille déterministe 5×5 (2 variables indépendantes, 25 scénarios)
- **Partie 3 — Comparaison H3** :
  - 6 métriques : richesse, variables, précision, risque tail, densité IC, régimes, stress
  - Tests statistiques (Kolmogorov-Smirnov)
  - Tableau de synthèse final

## Fichiers principaux
- `Monte_Carlo_IA_H3.ipynb` : notebook complet (code + résultats + figures)
- Figure exportée : `OCP_H3_Validation_Finale.png` (11 sous-graphiques comparatifs)

## Exécution
Ouvrir dans **Google Colab** ou **Jupyter Notebook**.  
Dépendances : `pandas`, `numpy`, `scikit-learn`, `scipy`, `matplotlib`, `seaborn`
