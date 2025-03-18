# Interface Utilisateur Streamlit pour l'API de Prédiction de Scoring de Crédit

## Contexte
La société financière **"Prêt à dépenser"** propose des **crédits à la consommation** à des personnes ayant **peu ou pas d'historique de prêt**. Pour évaluer le risque des demandes de crédit, une **API de scoring de crédit** a été mise en place, permettant de :

- Estimer la probabilité qu’un client présente des incidents de paiement.
- Classifier une demande de crédit en "acceptée" ou "refusée", selon un **seuil optimal** basé sur un modèle de prédiction entraîné sur des données déséquilibrées.

Afin de simplifier l’interaction avec cette API, une interface utilisateur a été développée en Streamlit. Elle permet aux utilisateurs de saisir directement un numéro de client pour obtenir une prédiction en toute simplicité.

Le code correspondant à l'API dans le repository GitHub [**modelisation_scoring**](https://github.com/SandraDOLLINGER/modelisation_scoring).

## Fonctionnement de l'Interface
L'interface Streamlit fournit un moyen simple et intuitif de communiquer avec l'API de scoring de crédit.
Voici les étapes pour l'utiliser :

- Lancer l'application Streamlit.
- Saisir le numéro du client dans le champ prévu à cet effet.
- Obtenir la prédiction en temps réel, affichant la probabilité que le client présente des incidents de paiement ainsi que la classification "crédit accepté" ou "crédit refusé".
## Structure du projet
- Application Streamlit

    - streamlit_scoring.py → Code principal de l'application Streamlit qui interagit avec l'API de prédiction.
    - requirements.txt → Liste des dépendances nécessaires pour faire fonctionner l'application Streamlit.
    - Procfile → Fichier de configuration pour le déploiement sur Heroku.
- Dossier API de Prédiction
L'API de prédiction est disponible dans un autre repository GitHub.
Elle contient :

    - fonction_api_prediction.py → Code de l'API qui fournit les prédictions.
    - df_sample.csv → Exemple de clients utilisés pour tester l'API.
    - modele_retenu.pkl → Modèle final entraîné pour les prédictions.
    - scaler.pkl → Standardisation des données utilisées pour la prédiction.
## Utilisation de l'Interface Streamlit
- Lancer l'application Streamlit

Installez les dépendances nécessaires via :

    pip install -r requirements.txt

Lancez l'application en utilisant la commande suivante :

    streamlit run streamlit_scoring.py

Une fois l'application lancée, accéder à l'interface Streamlit avec un navigateur et renseigner le numéro client dans le champ disponible.

- Fonctionnement de l'application

L'interface permet de saisir un numéro de client à 6 chiffres et d’obtenir une prédiction concernant le défaut de paiement.

- Les résultats de prédiction comprennent :

    - La probabilité que le client rembourse son crédit sans incident.
    - La classification de la demande de crédit : "accepté" ou "refusé", selon les résultats du modèle de scoring et l'application du seuil optimal.
## Déploiement sur Heroku
L’application Streamlit est déployée automatiquement sur Heroku.


Un Procfile est utilisé pour définir l’exécution de l'application.
Le fichier requirements.txt liste toutes les dépendances nécessaires pour le bon fonctionnement de l'application.

Le déploiement se fait de manière transparente dès que le code est poussé sur le repository GitHub.

## Code Source
Le code source complet de l'API de prédiction est disponible dans le repository GitHub suivant :
[modelisation_scoring](https://github.com/SandraDOLLINGER/modelisation_scoring)