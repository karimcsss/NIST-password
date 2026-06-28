# NIST-password
# Analyse de la Conformité des Mots de Passe (Normes NIST)

Ce projet fournit un script Python permettant d'analyser la robustesse et la conformité de mots de passe d'utilisateurs en se basant sur les recommandations du **NIST** (National Institute of Standards and Technology). L'objectif principal est de détecter les mots de passe trop courts ainsi que ceux fréquemment compromis afin de renforcer la sécurité des comptes d'une organisation.

## 🚀 Fonctionnalités

- **Exploration des données utilisateurs** : Chargement et affichage des identifiants et des informations d'un fichier utilisateur (`users.csv`).
- **Calcul et vérification de la longueur** : Analyse de la taille des mots de passe avec l'application d'un filtre pour identifier ceux ayant moins de 8 caractères (`too_short`).
- **Distinguer les mots de passe communs** : Confrontation des mots de passe à un dictionnaire de référence listant les 10 000 mots de passe les plus vulnérables du web (`10_million_password_list_top_10000.txt`).
- **Filtrage des utilisateurs à risque** : Extraction ciblée de la liste des mots de passe non conformes (par exemple, ceux qui échouent au test de longueur ou à la détection de mots de passe communs) pour inciter à leur renouvellement.

## 🛠️ Fichiers Requis pour l'Exécution

Pour que le notebook fonctionne correctement, assurez-vous d'importer ces deux fichiers dans votre espace de stockage Colab :
1. `users.csv` : Le fichier de données contenant la liste de vos utilisateurs et leurs mots de passe associés (colonnes : `id`, `user_name`, `password`).
2. `10_million_password_list_top_10000.txt` : La liste contenant les 10 000 mots de passe les plus fréquemment piratés ou utilisés.


## 📊 Étapes de traitement dans le Notebook

Le notebook applique la logique suivante à l'aide de la bibliothèque `pandas` :
- **Étape 1 :** Lecture et affichage des données du fichier `users.csv`.
- **Étape 2 :** Mesure de la longueur de chaque chaîne et calcul du volume d'utilisateurs dont le mot de passe est inférieur à la limite réglementaire (8 caractères).
- **Étape 3 :** Chargement du jeu de données des 10 000 mots de passe les plus courants.
- **Étape 4 :** Recherche d'une correspondance exacte des mots de passe des utilisateurs avec le dictionnaire de sécurité et isolation des lignes jugées vulnérables.

## 📦 Dépendances

- [Pandas](https://pandas.pydata.org/) - Structure de données et manipulation de tableaux de données complexes.
