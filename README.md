# Kaggle competition: Bag of Words Meets Bags of Popcorn
# Les données
L'ensemble de données étiquetées se compose de 50 000 critiques de films IMDB, spécialement sélectionnées pour l'analyse des sentiments.
Le sentiment des critiques est binaire, ce qui signifie que la note IMDB < 5 donne un score de sentiment de 0 et que la note ≥ 7 a un score de sentiment de 1.
L'ensemble de formation se compose de 25 000 critiques différentes de l'ensemble de test.

**Descriptions de fichiers fournis :**
- labelledTrainData - L'ensemble d'apprentissage étiqueté. Le fichier est délimité par des tabulations et comporte une ligne d'en-tête suivie de 25 000 lignes contenant un identifiant, un sentiment et un texte pour chaque avis.
- testData - L'ensemble de test. Le fichier délimité par des tabulations comporte une ligne d'en-tête suivie de 25 000 lignes contenant un identifiant et un texte pour chaque avis. Votre tâche consiste à prédire le sentiment pour chacun. 
- unlabeledTrainData - Un ensemble d'entraînement supplémentaire sans étiquettes. Le fichier délimité par des tabulations comporte une ligne précédente suivie de 50 000 lignes contenant un identifiant et un texte pour chaque avis.
- sampleSubmission - Un fichier de soumission d'échantillon délimité par des virgules au format correct.

L'ensemble de formation contient les 3 champs suivants :

- id - ID unique de chaque avis
- sentiment - Sentiment de l'examen ; 1 pour les avis positifs et 0 pour les avis négatifs
- avis - Texte de l'avis

# Modélisation
J'ai déployé 2 modèles : 
1- Le modèle BERT a été initié grâce au transformeur de HuggingFace 'fabriceyhc/bert-base-uncased-imdb'.
L'optimisation du modèle a été effectuée grâce à l'algorithme d'Adam avec un taux d'apprentissage (learning rate) de 5e−5 et le terme de correction de biais de epsilon = 1e−8.
2- Le modèle RoBERTa a été initié grâce au transformeur de HuggingFace 'aychang/roberta-base-imdb'.
L'optimisation du modèle a été effectuée grâce à l'algorithme d'Adam avec un taux d'apprentissage (learning rate) de 2e−5 et le terme de correction de biais de epsilon = 1e−8.

3- Le modèle a ensuite était évalué en effectuant 3 itérations (epoch) sur nos données d'entraînement par paquets (batch size) de 4 observations.
L'arrêt précoce a été rajouté pour arrêter la formation une fois que les performances du modèle cessent de s'améliorer sur l'ensemble de données de validation.
Et pour sauvegarder les poids du modèle ayant la meilleure performance, j'ai utilisé la classe de rappel ModelCheckpoint.

# Évaluation des performances
Nos simulations ont montré que RoBERTa atteint des meilleurs performances que BERT. En effet, la précision (accuracy) de **96.72%** et dont l'aire
sous la courbe ROC (AUC) est de **99.28%** contre une précision de 94.78% et une AUC de  98.87% pour le modèle BERT.

