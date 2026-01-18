## Présentation

La classification des séries temporelles d’images satellites est une tâche primordiale . Elle est le coeur de plusieurs applications:  

- La surveillance agricole  
- La détection de changements environnementaux  
- La gestion des ressources naturelles  

Le défi principal réside dans la **quantité limitée de données étiquetées** et la complexité spatiale et temporelle des images. 

Ce projet explore l’utilisation de **pré-entraînement auto-supervisé des modèles Transformer** pour la classification des séries temporelles d’images satellites. L’objectif est de **tirer parti des grandes quantités de données non étiquetées** afin d’améliorer la performance sur des tâches de classification supervisée avec des données limitées.


## Méthodologie


### 1. Prétraitement des données
- Normalisation des images satellites.
- Alignement temporel, spatial et spectral.  

### 2. Architecture du modèle
- **Architecture 1:**  temporel transformer
    - chaque pixel est répresenté seulement par l'information spectrale  à un instant t.
- **Architecture 2:**  spatio-temporel transformer
    - chaque pixel est représenté par l'information spectrale et l'information spatiale à travers le temps.
- **Architecture 3:**  fine tuning spatio-temporel transformer
   - cet architecture est composée de deux étapes: 
      - *Pré-entraînement auto-supervisé :**  Masked Image Modeling (MIM), Contrastive learning entre timestamps.
      - Fine-tuning supervisé sur un petit jeu de données annotées.
---
## Résultats

| Métrique | Modèle Auto-Supervisé | Modèle Supervisé Standard |
|----------|----------------------|-------------------------|
| Accuracy | 92.5%                | 85.0%                   |
| F1-score | 0.91                 | 0.83                     |
| Kappa    | 0.89                 | 0.80                     |

**Interprétation:**  
- Le pré-entraînement auto-supervisé et l'intégration de l'information spatiale améliore la précision, notamment pour les classes minoritaires.  
- La convergence est plus rapide lors du fine-tuning supervisé.  




