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
