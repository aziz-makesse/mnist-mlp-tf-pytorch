# MNIST Digit Classification using MLP (TensorFlow & PyTorch)

Ce projet a pour objectif de construire un **Perceptron Multicouche (MLP)** pour classifier les chiffres manuscrits du célèbre **dataset MNIST**, en utilisant deux frameworks populaires : **TensorFlow/Keras** et **PyTorch**.

---

## Objectif

Classer une image de chiffre manuscrit (28x28 pixels en niveaux de gris) en une des 10 classes possibles (0 à 9).


---

## Dataset

Le projet utilise le dataset **MNIST** :

- 60 000 images pour l’entraînement
- 10 000 images pour le test
- Chaque image est de taille **28x28 pixels** en niveaux de gris
- 10 classes : **chiffres de 0 à 9**

Les images sont automatiquement téléchargées via `tf.keras.datasets.mnist` ou `torchvision.datasets.MNIST`.

---

## Étapes du projet

### 1. Chargement des données

- Normalisation des pixels (valeurs entre 0 et 1)
- Redimensionnement : aplatissement en vecteurs de taille **784 (28x28)**

### 2. Architecture du MLP

Architecture commune utilisée dans **TensorFlow** et **PyTorch** :

Input: Flatten(28x28 → 784)
Dense 1: 128 neurones + ReLU
Dropout: 20%
Dense 2: 256 neurones + ReLU
Dense 3: 128 neurones + ReLU
Output: 10 neurones + Softmax

>  Activation utilisée : **ReLU**
>  
>  Sortie finale : **Softmax** sur 10 classes

### 3. Entraînement

- **Fonction de perte** :
  - `categorical_crossentropy` (TensorFlow)
  - `CrossEntropyLoss` (PyTorch)
- **Optimiseur** : `Adam`
- **Métrique** : `accuracy`
- **Époques** : 10
- **Batch size** : 32 ou 64

### 4. Évaluation

- Évaluation sur l’ensemble de test
- Affichage de la précision finale
- Optionnel : affichage de quelques prédictions correctes/incorrectes

---

## Résultats attendus

- Précision attendue : **≥ 97%** sur l’ensemble de test
- Affichage optionnel de quelques images avec leur prédiction
