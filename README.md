# Système de recommandation de fleurs basé sur Image Features

## Introduction
Ce projet vise à développer un **Système de Recommandation de Fleurs** qui utilise les caractéristiques des images. Il exploite les techniques de computer vision et de machine learning pour analyser les images de différentes fleurs, en tenant compte de la couleur, de la forme et du style, afin de recommander des fleurs similaires ou complémentaires aux utilisateurs.

## Données
Nous avons constitué un ensemble de données diversifié comprenant une variété de fleurs aux couleurs, tailles et styles différents. Assurez-vous que toutes les images sont dans un format uniforme (par exemple, JPEG, PNG). Nous disposons d'un échantillon de **49** images de fleurs.

## Méthodologie
Pour développer un système de recommandation basé sur les caractéristiques des images, nous avons suivi les étapes suivantes :
1. **Prétraitement des images** : Les images sont préparées pour l'extraction des caractéristiques en ajustant leur taille, en les convertissant en tableaux de données, puis en les prétraitant pour correspondre au format d'entrée requis par le modèle de réseau de neurones convolutionnels (CNN).
2. **Sélection du modèle pré-entraîné** : Un modèle de réseau de neurones convolutionnels  pré-entraîné, tel que **VGG16**, est sélectionné. Ce modèle, ayant été entraîné sur de vastes ensembles de données, est capable d'extraire des représentations visuelles puissantes.
3. **Extraction des caractéristiques**: Chaque image du jeu de données est passée à travers le modèle CNN sélectionné pour en extraire les caractéristiques. On obtient un vecteur de caractéristiques descriptif pour chaque image.
4. **Définition d'une métrique de similarité**: Une métrique de similarité est définie pour mesurer la distance entre les vecteurs de caractéristiques. La similarité cosinus est choisie pour évaluer la proximité entre les vecteurs de caractéristiques des images.
   
*Rappel*

La formule de la similarité est la suivante :

$$                                                                                                                  
\text{Similarité} = 1 - \frac{\vec{A} \cdot \vec{B}}{\|\vec{A}\| \times \|\vec{B}\|}                                                                              
$$                                                                                                                  

où :
- $\vec{A}$ et $\vec{B}$ sont les vecteurs de caractéristiques.
- $|\vec{A}\|$ et $|\vec{B}\|$ sont les normes  des vecteurs $\vec{A}$ et $\vec{B}$. 
5. **Classement et recommndation**: Les images sont classées en fonction de leur similarité avec une image d'entrée donnée. Le système recommande les **N éléments** les plus similaires,
 tout en s'assurant que l'image d'entrée n'est pas incluse parmi les recommandations pour éviter l'auto-recommandation.

## Résultats
Le système de recommandation a réussi à identifier des fleurs similaires  en se basant sur leurs caractéristiques visuelles. Les recommandations sont précises et pertinentes, reflétant correctement les couleurs, formes et styles des fleurs. Les résultats démontrent l'efficacité du modèle dans l'analyse et la suggestion d'options appropriées.
