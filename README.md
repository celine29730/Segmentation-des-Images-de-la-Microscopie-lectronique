# Segmentation-des-Images-de-la-Microscopie-lectronique

L’IA permet de simplifier et d’accélérer le travail des équipes d’imagerie, aujourd’hui majoritairement sur les étapes précliniques, en facilitant la lecture des images. Le CHRU a donc besoin d'un outil IA pour segmenter un tel type d'images.
Il vous demande de l'aide pour cet objectif.

## Contexte du projet

L’IA est aujourd’hui omniprésente dans la littérature scientifique de l’imagerie médicale, d’autant plus depuis le développement de nouveaux algorithmes appelés réseaux de neurones 
convolutifs.

En effet, à ce jour, l’IA est très utile dans le domaine de l’imagerie, sur deux volets : la classification des images et la segmentation des organes. Les algorithmes pour classifier 
les images peuvent permettre d’aider au diagnostic en classant une image dans une catégorie particulière de pathologie. Les algorithmes pour segmenter les images sont couramment 
utilisés sur tous les types d’imagerie et en routine au CHRU. C’est ainsi que l’IA permet un gain de temps aux praticiens à la fois pour le diagnostic ou lors d’interventions. 
Elle présente aussi l’avantage de contourner certains biais liés à l’interprétation de l’opérateur.

## Les données.

Les données proviennent du défi ISBI 2012 pour la segmentation des structures neuronales dans l'empilement de microscopie électronique.

Les données de formation sont un ensemble de 30 sections d'une section série de données de microscopie électronique à transmission (ssTEM) du cordon nerveux ventral de la larve du premier stade de la drosophile. Le microcube mesure 2 x 2 x 1,5 microns environ, avec une résolution de 4 x 4 x 50 nm / pixel. Chaque image a 512x512 pixels.

Les étiquettes binaires correspondantes (répertoire label) sont fournies en blanc pour les pixels des objets segmentés et en noir pour le reste des pixels (qui correspondent principalement à des membranes).

L'objectif étant de confronter nos images train avec les masks (labels) afin de pouvoir effectuer notre modèle de prédictions.

Les données sont disponibles au format TIF ou TIFF (Tagged Image File Format) qui est un format de fichier graphique bitmap (raster).

### Caractéristiques du format TIF

Le format TIFF est un ancien format graphique, permettant de stocker des images bitmap (raster) de taille importante (plus de 4 Go compressées), sans perdition de qualité et indépendamment des plates formes ou des périphériques utilisés (Device-Independant Bitmap, noté DIB).

Le format TIFF permet de stocker des images en noir et blanc, en couleurs réelles (True color, jusqu'à 32 bits par pixels) ainsi que des images indexées, faisant usage d'une palette de couleurs. Ce format peut être utilisé pour des images médicales.

Nous utiliserons google colab pour le lancement de notre modèle.

Nous allons dans un premier temps transformer nos images .tiff en format .png pour pouvoir construire le modèle et pour pouvoir l'exploiter par la suite.

## Visualisation de nos données train (jeu d'apprentissage)

Nous souhaitons établir ici une comparaison entre nos images et nos masks afin de pouvoir par la suite établir un modèle de prédiction sur nos images de test. 
Nous allons donc dans un premier temps visualiser nos images ainsi les masks associés sur le jeu d'entraînement.





