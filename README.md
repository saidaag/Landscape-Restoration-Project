# 📘 Landscape Restoration Project
### CycleGAN + Diffusion (Executable Notebook Guide)

Ce dépôt contient un notebook exécutable permettant de restaurer des images de paysages dégradés à l’aide d’un pipeline hybride en **deux étapes** :

1. **CycleGAN** pour la restauration structurelle globale.  
2. **Stable Diffusion (img2img)** pour le raffinement des textures et du réalisme.


## 🚀 Guide d'exécution (Kaggle)

### 1. Prérequis
- **Environnement :** Kaggle Notebook obligatoire pour les ressources GPU.
- **Accélérateur :** Activer **T4 x2**  
  *(Settings → Accelerator)*


### 2. Dataset (LHQ)
- Utiliser le **Landscapes dataset (LHQ 1024×1024)**.
- **Chemin cible :**  
  `/kaggle/working/project/data/B_healthy_filtered`
- Le notebook gère automatiquement le redimensionnement en **256×256** pour l'entraînement.


### 3. Ordre d’exécution des cellules (IMPORTANT)

 **Le notebook doit être exécuté STRICTEMENT de manière séquentielle.**

- Chaque cellule dépend des résultats de la cellule précédente.
- Sauter une cellule ou modifier l’ordre d’exécution entraînera des erreurs.

Méthodes recommandées :
- Cliquer sur **Run All**
- Ou exécuter les cellules **une par une, dans l’ordre**


### 4. Workflow du Pipeline
- **Entraînement :**  
  CycleGAN apprend la transformation entre paysages dégradés et paysages sains sans données appariées grâce à la **cohérence cyclique**.
- **Outputs :**  
  Les modèles `.pth`, les échantillons visuels sont stockés dans :  
  `project/outputs/`
- **Raffinement :**  
  La diffusion transforme les sorties du GAN en paysages plus réalistes visuellement.


### 5. Évaluation
- **Métriques utilisées :**
  - PSNR
  - SSIM
  - Temps d'inférence
- **Note importante :**  
  Les résultats montrent une amélioration visuelle nette, malgré un compromis possible sur les métriques de distorsion classiques.


### 👤 Auteurs
- **AGUERCHI Saida**
- **ELMAAZOUZI Souad**
- **BENAGUERRI Safaa**

### 🎓 Institution
Université Cadi Ayyad – Morocco

